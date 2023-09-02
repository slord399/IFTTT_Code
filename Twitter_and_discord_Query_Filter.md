Skip if matched with keyword + Output log entry ('Keyword Matched, Action Skipped!')
*IFTTT seems only catch non-paid character limit only



let ingredient_Text = Twitter.newTweetFromSearch.Text;
let searchTerm_Text =
  'keyword1' ||
  //  'Spare' ||
  //  '' ||
  //  '' ||
  //  '' ||
  //  '' ||
  //  '' ||
  //  '' ||
  //  '' ||
  //  '' ||
  //  '' ||
  //  '' ||
  //  '' ||
  //  '' ||
  //  '' ||
  //  '' ||
  'keyword2';

if (ingredient.indexOf(searchTerm) !== -1) {
  Discord.postMessageToChannel.skip('Keyword Matched, Action Skipped!');
}


=================
Skip if matched with keyword + Output log entry ('Keyword Matched, Action Skipped!')
*IFTTT seems only catch non-paid character limit only



let ingredient_Text = Twitter.newTweetFromSearch.Text;
let searchTerm_Text =
  'keyword1' ||
  //  'Spare' ||
  //  '' ||
  //  '' ||
  //  '' ||
  //  '' ||
  //  '' ||
  //  '' ||
  //  '' ||
  //  '' ||
  //  '' ||
  //  '' ||
  //  '' ||
  //  '' ||
  //  '' ||
  //  '' ||
  'keyword2';

if (ingredient_Text.indexOf(searchTerm_Text) !== -1) {
  // run the action
} else {
  Discord.postMessageToChannel.skip('Keyword Matched, Action Skipped!');
}
