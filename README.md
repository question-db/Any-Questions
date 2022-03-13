# Any Questions
FileMaker Database for Canvas LMS quiz questions

## Download
[Any Questions.zip](Any%20Questions.zip) which contains:<br />
* 'Any Questions.fmp12' database<br />
* Uncompressed 'Example Questions' QTI folder (ready for initial import test)<br />


## Requirements

1) FileMaker (version 16 or higher; database made with v. 19.4.2)
	* Options: [Trial](https://www.claris.com/trial/ "Claris FileMaker"), [Single User](https://store.claris.com/individuals "Claris FileMaker"), or site license

2) Base Elements Plugin: [Download](https://docs.baseelementsplugin.com/article/522-downloads)
	* required for Canvas quiz upload compatability

## Installation

1. Download/install
	* Filemaker
	* BaseElements [plugin](https://docs.baseelementsplugin.com/article/522-downloads "BaseElements")

2. Download and decompress: [Any Questions.zip](Any%20Questions.zip)<br />

3. Follow instructions in Any Questions "Startup" window

4. View [Features.md](Features.md) and [Feature log](feature_log.pdf) for more detailed information.

	* Caution: When prompted following the first run, please choose a Canvas developmental course for testing. While I have done my best to validate and test scripts, I am confident others will discover bugs, especially in the context of quiz import given that I do not use Canvas to manage quizzes. For example, 'quiz groups' are new to me and I only had a single example to test. Currently, the import for 'quiz groups' is only setup for multiple choice-formatted questions. However, the import currently creates duplicates. Moreover, if you may find the questions high-lighted in red after import, this indicates that the answer was not properly scraped from the XML because of embedded HTML. Enter an answer and it will go away. It would be great if others could send 'quiz group' examples for testing as I will unlikely invest time creating them simply so I can re-import them.

5. Discover a problem or have a suggestion, post an [issue](https://github.com/question-db/Any-Questions/issues) so it can be investigated/considered.

