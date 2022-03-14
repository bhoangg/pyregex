#Regex

## Letters
```
Match   abcdefg
Match   abcde
Match   abc
```
Pattern: 'abc'

## Digits
```
Match   abc123xyz
Match   define "123"
Match   var g = 123;
```
Pattern: '123'


## Any charater
```
Match   cat.
Match   896.
Match   ?=+.
Skip    abc1
```
Pattern: '...\.'

## Only abc
```
Match	can
Match	man
Match	fan
Skip	dan
Skip	ran
Skip	pan
```
Pattern: '[cmf]an'

## Not abc
```
Match	hog	
Match	dog	
Skip	bog
```
Pattern: '[^b]og'

## Character ranges
```
Match	Ana
Match	Bob
Match	Cpc
Skip	aax
Skip	bby
Skip	ccz
```
Pattern: '[A-C][n-p][a-c]'

## Repetitions:
```
Match	wazzzzzup
Match	wazzzup
Skip	wazup
```
Pattern: 'waz{3,5}up'

## Zero/one or more repetitions:
```
Match	aaaabcc
Match	aabbbbc
Match	aacc
Skip	a
```
Pattern: 'aa+b*c+'

## Character optional
```
Match	1 file found?
Match	2 files found?
Match	24 files found?
Skip	No files found.
```
Pattern: '\d+ files* found\?'

## Any whitespace character
```
Match	1.   abc
Match	2.	abc
Match	3.           abc
Skip	4.abc
```
Pattern: '\d\.\s+abc'

## Staring and ending
```
Match	Mission: successful
Skip	Last Mission: unsuccessful
Skip	Next Mission: successful upon capture of target
```
Pattern: '^Mission: successful$'

## Capture group
```
Capture	file_record_transcript.pdf	file_record_transcript
Capture	file_07241999.pdf	        file_07241999
Skip	testfile_fake.pdf.tmp
```
Pattern: '^(file.+)\.pdf$'

## Capture subgroup
```
Capture	Jan 1987	Jan 1987 1987
Capture	May 1969	May 1969 1969
Capture	Aug 2011	Aug 2011 2011
```
Pattern: '(\w+ (\d.+))'

## Capture all
```
Capture	1280x720	1280 720
Capture	1920x1600	1920 1600
Capture	1024x768	1024 768
```
Pattern: '(\d+)x(\d+)'

## Matches abc or def
```
Match	I love cats
Match	I love dogs
Skip	I love logs
Skip	I love cogs
```
Pattern: 'I love (cats|dogs)'