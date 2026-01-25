
// Pick a value from your trigger that is unique for each feed item
// Most triggers have an 'Id' or a 'CreatedAt' field. 
// Replace 'Trigger.CreatedAt' with the appropriate field from your specific trigger.


// 1. Get the unique URL string
const seed: string = Feed.newFeedItem.EntryUrl;

// 2. A standard hash function to turn the string into a unique number
let hash: number = 0;
for (let i = 0; i < seed.length; i++) {
  const char = seed.charCodeAt(i);
  hash = ((hash << 15) - hash) + char;
  hash |= 0; // Convert to 32bit integer
}

// 3. Use the absolute value of the hash to find the bucket (0, 1, 2, 3, 4, 5, 6, 7, 8 or 9)
const bucket: number = Math.abs(hash) % 15;

// --- Webhook Distribution ---

if (bucket !== 0) {
  MakerWebhooks.makeWebRequest1.skip("Sent to bucket " + bucket);
}

if (bucket !== 1) {
  MakerWebhooks.makeWebRequest2.skip("Sent to bucket " + bucket);
}

if (bucket !== 2) {
  MakerWebhooks.makeWebRequest3.skip("Sent to bucket " + bucket);
}

if (bucket !== 3) {
  MakerWebhooks.makeWebRequest4.skip("Sent to bucket " + bucket);
}

if (bucket !== 4) {
  MakerWebhooks.makeWebRequest5.skip("Sent to bucket " + bucket);
}

if (bucket !== 5) {
  MakerWebhooks.makeWebRequest6.skip("Sent to bucket " + bucket);
}

if (bucket !== 6) {
  MakerWebhooks.makeWebRequest7.skip("Sent to bucket " + bucket);
}

if (bucket !== 7) {
  MakerWebhooks.makeWebRequest8.skip("Sent to bucket " + bucket);
}

if (bucket !== 8) {
  MakerWebhooks.makeWebRequest9.skip("Sent to bucket " + bucket);
}

if (bucket !== 9) {
  MakerWebhooks.makeWebRequest10.skip("Sent to bucket " + bucket);
}

if (bucket !== 10) {
  MakerWebhooks.makeWebRequest11.skip("Sent to bucket " + bucket);
}

if (bucket !== 11) {
  MakerWebhooks.makeWebRequest12.skip("Sent to bucket " + bucket);
}

if (bucket !== 12) {
  MakerWebhooks.makeWebRequest13.skip("Sent to bucket " + bucket);
}

if (bucket !== 13) {
  MakerWebhooks.makeWebRequest14.skip("Sent to bucket " + bucket);
}

if (bucket !== 14) {
  MakerWebhooks.makeWebRequest15.skip("Sent to bucket " + bucket);
}
