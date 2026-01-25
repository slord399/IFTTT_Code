let ingredient = Feed.newFeedItem.EntryTitle;

/**
 * Logic Mapping:
 * Match Keyword 1 -> Skip 2, 3, 4, 5, 6
 * Match Keyword 2 -> Skip 1, 3, 4, 5, 6
 * Match Keyword 3 -> Skip 1, 2, 4, 5, 6
 * Match Keyword 4 -> Skip 1, 2, 3, 5, 6
 * Match Keyword 5 -> Skip 1, 2, 3, 4, 6
 * Match Keyword 6 -> Skip 1, 2, 3, 4, 5
 * No Match        -> Skip 2, 3, 4, 5, 6 (Only Request 1 runs)
 */

// Define the mapping
const config = [
  { key: "<keyword1>",           skipFunc: () => MakerWebhooks.makeWebRequest1.skip("Keyword not matched") },
  { key: "<keyword2>",         skipFunc: () => MakerWebhooks.makeWebRequest2.skip("Keyword not matched") },
  { key: "<keyword3>",        skipFunc: () => MakerWebhooks.makeWebRequest3.skip("Keyword not matched") },
  { key: "<keyword4>", skipFunc: () => MakerWebhooks.makeWebRequest4.skip("Keyword not matched") },
  { key: "<keyword5>",   skipFunc: () => MakerWebhooks.makeWebRequest5.skip("Keyword not matched") },
  { key: "<keyword6>",     skipFunc: () => MakerWebhooks.makeWebRequest6.skip("Keyword not matched") }
];

// 1. Find the match
let matchedIndex = -1;
for (let i = 0; i < config.length; i++) {
  if (ingredient.indexOf(config[i].key) !== -1) {
    matchedIndex = i;
    break;
  }
}

// 2. Execute Skips
if (matchedIndex !== -1) {
  // A keyword matched. Skip all actions EXCEPT the one that matched.
  for (let j = 0; j < config.length; j++) {
    if (j !== matchedIndex) {
      config[j].skipFunc();
    }
  }
} else {
  // No keyword matched. 
  // Run WebRequest 1 (meaning skip 2, 3, 4, 5, and 6).
  MakerWebhooks.makeWebRequest2.skip("Keyword not matched");
  MakerWebhooks.makeWebRequest3.skip("Keyword not matched");
  MakerWebhooks.makeWebRequest4.skip("Keyword not matched");
  MakerWebhooks.makeWebRequest5.skip("Keyword not matched");
  MakerWebhooks.makeWebRequest6.skip("Keyword not matched");
}
