## How I completed this project

### TODO (after P3 is completed)
1. Review against the Project Rubric.
2. Submit it according to the Submission Instructions on the portal.

My repository includes the following files from the original fork:

* **index.html**: The main HTML document. Contains links to all of the CSS and JS resources needed to render the resume, including resumeBuilder.js.

_This file is unchanged from the one supplied by Udacity_.
* **js/helper.js**: Contains helper code needed to format the resume and build the map.

_I made some minor additions to this file. More on helper.js further down_.
* **js/resumeBuilder.js**: This is wot I did done.
* **js/jQuery.js**: The jQuery library.
* **css/style.css**: Contains all of the CSS needed to style the page.

_This file was far from following the Udacity Style Guide and there wasn't much value in me fixing it. This also discouraged me from really making the resume 'my own'_.
* **README.md**: This file right here. Markdown. _Why?_
* and some custom images in the images directory.

My repository also includes:

* **.gitignore**: git file that helps stop me uploading windows Thumbs.db files and other things
* **js/jqueryui.min.js**: for 'udacious' interactive layout manipulation (accordion effect)
* **css/jqueryui.min.css**: required by jqueryui

### The process:
The resume has six distinct sections: work, education, projects, an interactive map, a header with biographical information and a footer with quick contact information.

1. All section draw their data from four JSON-like objects, containing work, biography, education and projects information. The objects also contain a method to write that data to the page.
The objects I created originall followed the names within the schema below exactly. And they were confirmed to be formatted correctly with <a href="http://jsonlint.com/" target="_blank">JSONlint.com</a>. However, once the display methods were included, they were no longer valid JSONs. There are some further additions made to the schema based on making the resume 'udacious' and adding standard functionality such as contact details with clickable links. e.g. twitter address will link to a twitter profile. This was also suggested by an instructor on the Piazza forums, I think.
The **bolded** items show additions and / or deviations.
  <ul>
    <li>`bio` contains:
      <ul>
        <li>name : string</li>
        <li>role : string</li>
        <li>contacts : an object with
          <ul>
            <li>mobile: <strong>object with a string value and string uri</strong></li>
            <li>email: <strong>object with a string value and string uri</strong></li>
            <li>github: <strong>object with a string value and string url</strong></li>
            <li>twitter: <strong>object with a string value and string url</strong></li>
            <li>location: string</li>
          </ul>
        </li>
        <li>welcomeMessage: string</li>
        <li>skills: array of strings</li>
        <li>biopic: url</li>
        <li>display: function taking no parameters</li>
      </ul>
    </li>
    <li>`education` contains:
      <ul>
        <li>schools: array of objects with
          <ul>
            <li>name: string</li>
            <li>location: string</li>
            <li>degree: string</li>
            <li>majors: array of strings</li>
            <li>dates: integer (graduation date)</li>
            <li>url: string</li>
          </ul>
        </li>
        <li>onlineCourses: array with
          <ul>
            <li>title: string</li>
            <li>school: string</li>
            <li>date: integer (date finished)</li>
            <li>url: string</li>
          </ul>
        </li>
        <li>display: function taking no parameters</li>
      </ul>
    </li>
    <li>`work` contains
      <ul>
        <li>jobs: array of objects with
          <ul>
            <li>employer: string</li>
            <li>title: string</li>
            <li>location: string</li>
            <li>dates: string (works with a hyphen between them)</li>
            <li>description: string</li>
          </ul>
        </li>
        <li>display: function taking no parameters</li>
      </ul>
    <li>`projects` contains:
      <ul>
        <li>projects: array of objects with
          <ul>
            <li>title: string</li>
            <li>dates: string (works with a hyphen between them)</li>
            <li>description: string</li>
            <li>images: <strong>object with string urls and string alt text values</strong></li>
          </ul>
        </li>
        <li>display: function taking no parameters</li>
      </ul>
    </li>
  </ul>
2. I added the code and content as per the course materials.
3. The resume includes an interactive map. To add it, I appended the googleMap string to `<div id=”mapDiv”>`. I then found some functionality in the Google Maps online documentation and add some basic info the the place markers when clicked on.
4. The instruction call for all of the code for adding elements to the resume to be within functions, and all of the functions to be encapsulated within the same objects containing your resume data. This apparantly contradicts the requirement for the JSON objects to validate, so faced with a choice, I chose to do this and have objects that don't validate. In my own projects I would prefer not do this, I would keep the display functions seperate and have valid JSON.
5. My resume also includes `console.log()` information about click locations. I made a small easter egg addition to this function by adding some code to the helper.js file to hopefully help alleviate some boredom for the marking turks at Udacity (if there are any!).