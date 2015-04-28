## Latest Javadocs ##
The latest Javadocs for the ESAPI can be found [here](http://owasp-esapi-java.googlecode.com/svn/trunk_doc/index.html).

## How to create Javadocs for ESAPI using Eclipse v3.4 ##
First off, notice a folder called "javadoc resources" in the root directory of your ESAPI project.  This folder contains images referenced from the Javadoc as well as overview-summary.html, which is the title page for the ESAPI Javadoc.  The instructions below make reference to these files.
[[category:FIXME|image links not working]]
### To Generate Javadocs ###
  1. ''Be sure you are in the Java EE perspective.''  To change your perspective, click the ''Window'' button on the main toolbar.  Then click ''Open Perspective'' and choose ''Java EE''.  If Java EE is not in the list, select ''Other...'' and find ''Java EE''.  If Java EE is not in the list under Other, you may need to download Eclipse Ganymede (v3.4) for Java EE developers.  Javadoc creation functionality may be built into your version of Eclipse, but that has not been tested.
  1. Then, click the ''Project'' button on the main toolbar.  Select ''Generate Javadoc...''
  1. Find the Javadoc executable to use.  This is usually javadoc.exe within your java bin directory, as shown in figure 1.
  1. Select the ESAPI source, but not the test files within your ESAPI project, as shown in figure 1.
  1. You should create Javadoc for members with visibility: Package, as shown in figure 1.
  1. Select the Javadoc output directory.  This will likely be /doc under your ESAPI project folder.
  1. Click ''Next''.

Figure 1:

![http://owasp-esapi-java.googlecode.com/svn/trunk/documentation/Generate%20Javadoc1.jpg](http://owasp-esapi-java.googlecode.com/svn/trunk/documentation/Generate%20Javadoc1.jpg)

  1. Designate a title for this Javadoc.  Generally, this should be "OWASP Enterprise Security API (ESAPI)".
  1. Use Default: Under Basic Options, make sure all checkboxes are selected, as shown in Figure 2.
  1. Use Default: Make sure Javadocs for referenced archives are not generated, as shown in Figure 2.
  1. Use Default: No custom style sheet should be specified, as shown in Figure 2.
  1. Click ''Next''.

Figure 2:

![http://owasp-esapi-java.googlecode.com/svn/trunk/documentation/Generate%20Javadoc2.jpg](http://owasp-esapi-java.googlecode.com/svn/trunk/documentation/Generate%20Javadoc2.jpg)

  1. ''The Overview page must be selected, as shown in Figure 3''.  ''It should point to overview-summary.html in the javadoc resources folder''.
  1. Use Default: The JRE source compatibility should be selected as 1.4, as shown in Figure 3.
  1. Click ''Finish''.

Figure 3:

![http://owasp-esapi-java.googlecode.com/svn/trunk/documentation/Generate%20Javadoc3.jpg](http://owasp-esapi-java.googlecode.com/svn/trunk/documentation/Generate%20Javadoc3.jpg)

  1. If it isn't already there, copy the folder "doc-files" from "javadoc resources" to org/owasp/esapi within your new javadoc directory.
  1. To view these new javadocs, double click on: 

&lt;yourdocsfolder&gt;

/index.html

### Submitting these new javadocs to SVN ###
  1. To submit these newly generated javadocs, simply use Team --> Commit in Eclipse. Note: Please check in updates into the existing /doc directory, rather than creating a new directory.
  1. If you receive version control errors during the submit, follow the following steps:
  * Navigate to your ESAPI Project/doc/org/owasp/esapi/doc-files directory.
  * Delete the folder called .svn from this folder and all subdirectories (wiki).
  * In the Navigator view in Eclipse, Right-click the doc-files folder and select "Team" -> "Add to svn:ignore...".
  * In the Navigator view in Eclipse, Right-click the doc-files folder again and select "Team" -> "Add to Version Control".  You should receive a message saying that you previously asked to ignore this file.  Click yes.

## Why do my newly generated Javadocs render as plain text in my browser? ##
Unfortunately, using this method of Javadoc generation does not set MIME types for the HTML files generated.  This means that to the browser, your HTML files are just text files, and will display as such.  Luckily Subclipse has a function to fix this.  We are going to tell Subclipse to automatically set the MIME type of HTML files to text/html and the MIME type of CSS files to text/css every time it commits a change.

  1. The first thing you need to do is enable auto properties for your SVN client.  If you do not enable auto properties, you will have to manually set the properties (MIME type) of every HTML and CSS file.
  * In Windows, open a terminal by typing "cmd" (with no quotes) into "Run" on the Start menu.  If you are using Vista, you can type "cmd" directly into the "Start Searching" bar.
  * Type (again, and from now on, with no quotes) "cd %APPDATA%" and hit enter.
  * Type "cd Subversion" and hit enter.
  * Type "notepad config". This will open the SVN configuration file in notepad.
  * Find the line "enable-auto-props = yes" and remove the   # from the front of it.  This enables auto properties.
  1. Then, tell Subversion which MIME types to set for which files:
  * Towards the bottom of the file, find a section called ''[auto-props]''.  Add the following to this section:
    * html = svn:mime-type=text/html
    * css = svn:mime-type=text/css
  1. Save the file.
''Any further commits to the SVN should set the MIME type properly.''

Your Javadoc should be ready to commit and view!