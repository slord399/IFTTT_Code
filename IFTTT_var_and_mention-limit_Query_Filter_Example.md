// Add your code here. All actions will run unless you explicitly skip them.
// Quick tips!
// Auto-complete is on. Start typing to see ingredient options.
// Hover over any ingredient to see the variable type and an example.
// TypeScript v2.92

var ingredient_Text = Twitter.newTweetFromSearch.Text;

var searchTerm_Text = [
  'abc',
  'efg',
];

let ingredient_Username = Twitter.newTweetFromSearch.UserName;
var searchTerm_username = [
  '111',
  '222',
];

let keywordMatched = false;

// Count @ within term
var atCount = (ingredient_Text.match(/@/g) || []).length;

// If @ included be 4+, skip action
if (atCount >= 4) {
  MakerWebhooks.makeWebRequest.skip('Too many @ symbols, Action Skipped!');
} else {
  // Keyword Check
  for (var i = 0; i < searchTerm_Text.length; i++) {
    var texts = searchTerm_Text[i];
    if (ingredient_Text.toLowerCase().indexOf(texts.toLowerCase()) !== -1) {
      keywordMatched = true;
      break;
    }
  }

  if (!keywordMatched) {
    for (var j = 0; j < searchTerm_username.length; j++) {
      var usernames = searchTerm_username[j];
      if (
        ingredient_Username.toLowerCase().indexOf(usernames.toLowerCase()) !== -1
      ) {
        keywordMatched = true;
        break;
      }
    }
  }

  if (keywordMatched) {
    MakerWebhooks.makeWebRequest.skip('Keyword Matched, Action Skipped!');
  }
}
