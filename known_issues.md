## Known Issues/Limitations

## 1. Importing quiz questions into the database
1. 'quiz groups'
	* multiple choice questions are the only format currently implemented
2. question formats
	* all formats:
		* feedback import is limited to 'general', 'incorrect/correct' feedback import is not implemented
		* Embedded HTML is stripped from questions to avoid making a mess during import.
		* Incorrectly-formatted HTML in answer options can lead to an inability to capture the correct answer. I've noticed this for some publisher-provided questions. If questions are high-lighted in red after import, the script failed to scrape the answer from the XML. Enter an answer for the effected question in the database and the red will go away.
	* multiple choice: if the correct answer is listed first on Canvas, it will be imported as answer “A” in the database given that import scripts scrape the data in the order found in the XML. To avoid all multiple choice answers being “A” after re-exporting, either: A) select shuffle answers when exporting the quiz or B) rearrange the answers manually in the question database.

	* file upload: format not currently implemented
	* numerical: 'answer in range' is the only format currently implemented (need real world examples for 'exact answer' and 'answer with precision')
	* matching: distractors are not imported (cannot figure out how to consistently accomplish this)
	* table format: not properly re-imported when the question type is created with Any Questions given that this format does not exist in Canvas.
3. quiz question order is not preserved during import
4. questions in data tables (CSV, Excel, TAB, etc):
	* Requires a template for efficient import. If there is interest, these can be created.
	* Question-associated figures/images need to be manually imported into the database
5. exported QTI packages have a subfolder named after the folder in which the files are stored on Canvas. It contains all quiz-associated figures as long as the user has the appropriate file permissions. In a multi-instructor setting, figures may be missing if an instructor stores figures in their userspace. This is a Canvas limitation.
6. Quiz settings
	* Quiz-specific settings (i.e. instructions, dates, time allowed, etc) are not imported. This is possible, but I'm not sure I see the point.
7. If quiz import path has special characters, the script may fail


## 2. Exporting quizzes to Canvas
1. question formats
	* all formats: Canvas does not honor the 'height' tag of images/figures following import, but does honor the 'width' flag. As such, the database proportionally scales the image based on the image width specified in the figure settings.
	* Essay: Canvas does not allow inclusion of an answer in the essay format.
2. General: if a quiz export is not allowed to complete or is prematurely canceled, this may cause the import to lock up. Evidence of this is obvious on the Import status page where it says "pre-processing". In this event, there are two options: 1) allow Canvas to clear the problem automatically (which can take up to 24 hrs) or 2) reset the course page. As a consequence, be sure to test exports using the developmental course.
3. Question formating:
	* Any text in the 'question' section can be formatted using Filemaker. Formats ( italic, underline, etc) will be sent to Canvas in HTML automatically. Unfortunately. instead of *strong* /bold Filemaker uses "font style" which is not recognized by Canvas.
	* The following characters are substituted automatically in CSS transform to comply with XML constraints <,>, ", ', &.
	* Unicode characters for lowercase Greek alphabet are hard-coded (i.e. &alpha; → &#x3B1) and should be automatically converted into XML-compliant format. Other Unicode characters will need to be added individually. If formatted HTML is buggy on Canvas after export, check for Unicode characters.
4. Rapid/repeated quiz upload:
	* Quizzes can be uploaded faster than Canvas servers can process (depending on Canvas server load at any particular time of day). This can cause quizzes to become out of register with the database. If this happens multiple quizzes with identical names will be present on Canvas. Thus, if a user tries to delete a specific quiz, multiple delete cycles will be needed to clear all copies.
5. Proctorio:
	* If Proctorio is selected for quiz monitoring, the specific settings may not be as expected given that these settings are specified using a quiz-specific character string generated when the quiz is generated on Canvas — which cannot be duplicated remotely. If someone knows how to capture this data, please let me know.
6. Respondus:
	* This is completely untested as I have never used it. The setting simply tells Canvas to activate the setting.
7. Quiz format
	* quiz format is properly set in the XML, but is not honored by Canvas. All quizzes are imported as 'graded quiz'.

## 3. Export quiz to HTML for printing
1. Question formats
	* matching: Question answers are not randomized during export and must be changed manually. This is indicated in the exported HTML to draw awareness to the issue.
2. Exported HTML is not automatically imported into any text editor (i.e. Word) given potential difference in user-specific applications.

## 4. Database
1. Questions and Quizzes:
	* for tagging functionality, new questions and quizzes should be generated by clicking their respective icons so unique UUIDs are created (avoid using Filemaker menu 'Create New').
		* a solution to this limitation is to dynamically calculate UUIDs (my original implementation), However, doing so precludes the ability to properly import datasets from old databases with their question-associated tags (stored in related tables). Not sure how to solve this.
2. Searching using tags:
	* Currently one can search by any combination of criteria on a layout with the exception that only one tag can be searched at a time. For example, searching for a 'Quiz" and "Date" tag does not return a result. I don't understand this, but it may be a FileMaker limitation when a search involves multiple related tables.
3. Quiz id capture:
	* Quiz-specific ids are captured based on the quiz name. As such, quizzes with names that do not exist in the database are captured, but cannot be linked to questions.
4. Hyperlinks:
	* 'Go to quiz preview' does not directly bring users to the expected location.
