# Any Questions
## FileMaker Database for Canvas LMS quiz questions<br />

The database is intended for use by instructors as an offline tool to manage course exam/quiz questions with the ability to either post quizzes to Canvas or export for printing.<br />


* I currently consider the database 'alpha' code given that:
	1. additional features are still being added to facilitate more general use
	2. the database has only  been tested by me
* If/when someone provides feedback, I will move the database to 'beta' and start a change log
* When I discover an issue on my end, I post an updated database when it is fixed

## Download
[Any_Questions.zip](Any_Questions.zip) which contains:<br />
* Any Questions_v[#.#a].fmp12 — FileMaker database file
* Example Questions — uncompressed QTI folder (ready for initial import test)
* quick_start.pdf — illustrated guide to database layout and functions


## Requirements

1) FileMaker (version 16 or higher; database made with v. 19.4.2)
	* Options: [Trial](https://www.claris.com/trial/ "Claris FileMaker"), [Single User](https://store.claris.com/individuals "Claris FileMaker"), or site license

2) Base Elements Plugin: [Download](https://docs.baseelementsplugin.com/article/522-downloads)
	* required for Canvas QTI quiz compression

## Installation

1. Download/install
	* Filemaker
	* BaseElements [plugin](https://docs.baseelementsplugin.com/article/522-downloads "BaseElements")

2. Download and decompress: [Any_Questions.zip](Any_Questions.zip)<br />

3. Follow instructions in Any Questions "Startup" window
	* Note: If updating from a previous database version, please select the 'Import Previous Database' in the 'Startup' window.

4. View [Features.md](Features.md), [Feature log](feature_log.pdf), and [known issues](known_issues.md) for more detailed information.

	**Caution** <br />
	* When prompted following the first run, please choose a Canvas developmental course for testing. While I have done my best to validate and test scripts, I am confident others will discover bugs, especially in the context of quiz import given that I do not use Canvas to manage quizzes. For example, 'quiz groups' are new to me and I only had a single example to test. <br />
	* 'Quiz groups' are currently only setup to import multiple choice-formatted questions.
	* If questions are high-lighted in red after import, the script failed to scrape the answer from the XML. This results from extra HTML-embedded code in the answer. Enter an answer in the database and it will go away.
	* It would be great if others could send 'quiz group' examples for testing as I will unlikely invest time creating them simply so I can re-import them.

5. Discover a problem not listed in the [known issues](known_issues.md) or have a suggestion, post an [issue](https://github.com/question-db/Any-Questions/issues) so it can be investigated/considered.

