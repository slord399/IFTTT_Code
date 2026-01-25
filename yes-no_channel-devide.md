
let ingredient = Feed.newFeedItem.EntryTitle;
let searchTerm = '<keyword>';

if (ingredient.indexOf(searchTerm) !== -1) {
  // Skip the first webhook if the keyword is found
  MakerWebhooks.makeWebRequest1.skip("This is promotional feed");
} else {
  // Skip the second webhook if the keyword is not found
  MakerWebhooks.makeWebRequest2.skip("This isn't promotional feed");
}
