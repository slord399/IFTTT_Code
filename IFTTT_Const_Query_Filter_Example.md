const ingredient_Text = Twitter.newTweetFromSearch.Text;

// Find all the occurrences of the keywords in the text.
const greetings: string[] = [
  'おはよ',
  'おはっぱ',
  'おはやん',
  'おっは',
  'おはまこ',
  'おはれむ',
  'おはと',
  'オハヨ',
  'おはさよ',
  'おはっぴ',
  '아침',
  '좋은아침',
  'おはてー',
  'おはこと',
  'おはあい',
  'おﾞあﾞよﾞ',
  'おはやみ',
  'ｵﾊﾏﾙ',
  'おはみざ',
  'おはたら',
  'もにもに',
  'おはこに',
  'おはじど',
  'おはる',
  'ohaRIYO',
  'おはこ',
  'おはろ',
  'おはうぎ',
  'おはみあ',
  'おはごじゃます',
  'おはけみ',
  'おはべり',
  'おはえの',
  'おはみ',
  'おはりっと',
  'おはみき',
  'おはめり',
  'おはやた',
  'おはんにょ',
  'おはしのる',
  'おはもふ',
  'おはきゃっと',
  'おぁよ',
  'おはりむ',
  'おはしゃけ',
  'おはこー',
  'おはつっき',
  'おはなゆ',
  'ohayo',
  'おはあ',
  'おはうぃず',
  'おはりふぉ',
  'おはりと',
  'おはろこ',
  'おはてり',
  'おはやも',
  'おはみな',
  'おはしま',
  'おはみ～',
  'グットレンドモーニング',
  'おっはてぃ',
  'おはすー',
  'おはさな',
  'あささつき',
  'おはれーじ',
  'おはせん',
  'おはてーな',
  'おはしろ',
  'おはさめ',
  'おはうづ',
  'おはじゅい',
  //
  //
  //
  //
  //

  'お休みなさい',
  'おやすみなさい',
  'おやすみ',
  'しごおわ',
  //
  //
  //
  //
  //
  '#美少女発掘メーカー',
  '#巨根',
  '#見せ合い',
  'dmm.co.jp',
];

for (const greeting in greetings) {
  if (ingredient_Text.indexOf(greeting) !== -1) {
    // If a greeting is found, skip the rest of the code.
    MakerWebhooks.makeWebRequest.skip('Keyword Matched, Action Skipped!');
  }
}
