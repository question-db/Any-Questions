# Questions-Database
FileMaker Database for Canvas LMS quiz questions

## Requirements

1) FileMaker (version 16 or higher; database made with v. 19.4.2)
	• Download FileMaker
	• Options: I avoid the rental model 
		a) use 14 day Trial to evaluate: https://www.claris.com/trial/
		b) CBS site license (contact CBS IT)
		c) Single user license: https://store.claris.com/individuals
			• upgrade: $197
			• academic: $324 (full version only)
					
2) Base Elements Plugin
	• install after Filemaker
	• required for Canvas quiz upload and platform compatability
	• download: https://docs.baseelementsplugin.com/article/522-downloads

3) Canvas Course identification number
4) Canvas API token
	

## Installation

1) Download and install Filemaker
2) Download the Base Elements Plugin (BaseElements) 
	a) download plugin 
	b) decompress and note file location
	c) open Filemaker 
	d) drag the plugin into the Startup window in FileMaker
	e) click the 'Install Plugin' button
3) Following instructions in FileMaker database "Startup" window
	a) enter Canvas Course ID number
	B) enter API token for Canvas access via API
	
4) Optional: install example questions
	a) download question_exmaples.zip
	b) decompress file
	c) import into Questions
