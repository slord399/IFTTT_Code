(test1 OR test2 OR test3) min_faves:x -"ignore1" -"ignore2" -"ignore3" -"ignore4" -"ignore5"

=Ignore=
-keyword 　Broken
(-keyword)    Not Function
-"keyword"    Works Correctly

keyword1 OR keyword2     No Longer Works due to API change
(keyword1 OR keyword2)  Most of case, function
("keyword1" OR "keyword2") Best as it seems

Still need to debug further as often got wrong result still.
And....Twitter change API spec often.


=Following Method has been removed recently=
-nativetweets
filter:
exclude:
