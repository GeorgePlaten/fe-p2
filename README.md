## How did I complete this project?

### TODO (after P3 is completed)
1. Review your work against the Project Rubric.
2. Submit it according to the Submission Instructions on the portal.

My repository includes the following files from the original fork:

* **index.html**: The main HTML document. Contains links to all of the CSS and JS resources needed to render the resume, including resumeBuilder.js. _This file is unchanged from the one supplied by Udacity_.
* **js/helper.js**: Contains helper code needed to format the resume and build the map. _I made some minor additions to this file. More on helper.js further down_.
* **js/resumeBuilder.js**: This is wot I did done.
* **js/jQuery.js**: The jQuery library.
* **css/style.css**: Contains all of the CSS needed to style the page. This file was far from following the Udacity Style Guide and there wasn't much value in me fixing it. This also discouraged me from really making the resume 'my own'.
* **README.md**: This file right here. Markdown. Why?
* and some custom images in the images directory.

My repository also includes:

* **.gitignore**: file
* **js/jqueryui.min.js**: for 'udacious' interactive layout manipulation (accordion effect)
* **css/jqueryui.min.css**: required by jqueryui

### The process:
The resume has six distinct sections: work, education, projects, an interactive map, a header with biographical information and a footer with quick contact information.

1. All section draw their data from four JSON-like objects, containing work, biography, education and projects information. The objects also contain a method to write that data to the page.
The objects I created originall followed the names within the schema below exactly. And they were confirmed to be formatted correctly with <a href="http://jsonlint.com/" target="_blank">JSONlint.com</a>. However, once the display methods were included, they were no longer valid JSONs. There are some further additions made to the schema based on making the resume 'udacious' and adding standard functionality such as contact details with clickable links. e.g. twitter address will link to a twitter profile. This was also suggested by an instructor on the Piazza forums, I think.

The **bolded** items show additions and / or deviations.

* `bio` contains:

            name : string
            role : string
            contacts : an object with
                  mobile: **object with a string value and string uri**
                  email: **object with a string value and string uri**
                  github: **object with a string value and string url**
                  twitter: **object with a string value and string url**
                  location: string
            welcomeMessage: string
            skills: array of strings
            biopic: url
            display: function taking no parameters

* `education` contains:

            schools: array of objects with
                 name: string
                 location: string
                 degree: string
                 majors: array of strings
                 dates: integer (graduation date)
                 url: string
            onlineCourses: array with
                 title: string
                 school: string
                 date: integer (date finished)
                 url: string
            display: function taking no parameters

* `work` contains

            jobs: array of objects with
                 employer: string
                 title: string
                 location: string
                 dates: string (works with a hyphen between them)
                 description: string
            display: function taking no parameters

* `projects` contains:

            projects: array of objects with
                  title: string
                  dates: string (works with a hyphen between them)
                  description: string
                  images: **object with string urls and string alt text values**
            display: function taking no parameters

2. I added the code and content as per the course materials.
3. The resume includes an interactive map. To add it, I appended the googleMap string to `<div id=”mapDiv”>`. I then found some functionality in the Google Maps online documentation and add some basic info the the place markers when clicked on.
4. The instruction call for all of the code for adding elements to the resume to be within functions, and all of the functions to be encapsulated within the same objects containing your resume data. This apparantly contradicts the requirement for the JSON objects to validate, so faced with a choice, I chose to do this and have objects that don't validate. In my own projects I would prefer not do this, I would keep the display functions seperate and have valid JSON.
5. My resume also includes `console.log()` information about click locations. I made a small easter egg addition to this function by adding some code to the helper.js file to hopefully help alleviate some boredom for the marking turks at Udacity (if there are any!).