# Any Questions
## FileMaker Database for Canvas LMS quiz questions<br />

The application is intended for use by instructors as an offline tool to create and remotely manage course exam/quiz questions. It can import/post quizzes from/to Canvas, export quizzes to print, and archive quizzes for storage. The only comparable tool of which I'm aware is Respondous. However, Respondous is not available on a Mac.<br />


* Although stable, I currently consider the application 'beta' code given that:
	1. additional features are continually being added to facilitate more general use
	2. the database has been tested by a variety of Canvas users at multiple institutions.
* When I discover an issue or decide on a new feature, I generally implement a fix and post an updated database, so feel free to check back.
* The application 'should' be Windows compatible, although export scripts have not be tested given that I use a Mac. If someone tests the application on Windows and discovers that export scripts do not work, it results from file path differences between platforms. If you try it and it does not work, please let me know by posting an issue.

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
	* When prompted following the first run, please choose a Canvas developmental course for testing. While I have done my best to validate and test scripts, I am confident others will discover bugs, especially in the context of quiz import given that I do not use the Canvas webpage to manage quizzes. For example, 'quiz groups' are new to me and I only had a single example to test. <br />
	* 'Quiz groups' are currently only setup to import multiple choice-formatted questions.
	* If questions are high-lighted in red after import, the script failed to scrape the answer from the XML. This results from extra HTML-embedded code in the answer. Enter an answer in the database and it will go away.
	* It would be great if others could send 'quiz group' examples for testing — it is unlikely that I will invest time creating them simply so I can re-import for testing.

5. Discover a problem not listed in the [known issues](known_issues.md) or have a suggestion, post an [issue](https://github.com/question-db/Any-Questions/issues) so it can be investigated/considered.

