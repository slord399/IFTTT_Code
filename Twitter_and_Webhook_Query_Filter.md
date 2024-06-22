Skip if matched with keyword + Output log entry ('Keyword Matched, Action Skipped!')

*IFTTT seems only catch non-paid character limit only


```
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
  MakerWebhooks.makeWebRequest.skip('Keyword Matched, Action Skipped!');
}
```

=================

Skip if matched with keyword + Output log entry ('Keyword Matched, Action Skipped!')

*IFTTT seems only catch non-paid character limit only


```
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
  MakerWebhooks.makeWebRequest.skip();
}
```


===============
Skip if matched keyword or username + Output log entry ('Keyword Matched, Action Skipped!')
(Multi ingredient usage be bit tricky as it seems, you need to complete within 1 flow even has few ingredient)

```
var ingredient_Text = Twitter.newTweetFromSearch.Text;

var searchTerm_Text = [
  'ABC',
  '123',
  'xyz',
];

let ingredient_Username = Twitter.newTweetFromSearch.UserName;
var searchTerm_username = [
  'abc',
  'dedf',
  'dedf',
];

let keywordMatched = false;

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
      ingredient_Username.toLowerCase().indexOf(usernames.toLowerCase()) !==
      -1
    ) {
      keywordMatched = true;
      break;
    }
  }
}
```
if (keywordMatched) {
  MakerWebhooks.makeWebRequest.skip('Keyword Matched, Action Skipped!');
}
