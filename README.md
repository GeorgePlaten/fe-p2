## How I completed this project

An alternate <a href="http://georgeplaten.github.io/fe-p2/resume/">live version of the completed resume can be viewed here</a>.

My repository includes the following files from the original fork:

* **index.html**: The main HTML document. Contains links to all of the CSS and JS resources needed to render the resume, including resumeBuilder.js.
_This file is unchanged from the one supplied by Udacity_.
* **js/helper.js**: Contains helper code needed to format the resume and build the map.
_I made a minor addition to this file. More on helper.js further down_.
* **js/resumeBuilder.js**: This is wot I did done.
* **js/jQuery.js**: The jQuery library.
* **css/style.css**: Contains all of the CSS needed to style the page.
_This file was far from following the Udacity Style Guide and there wasn't much value in me fixing it. This also discouraged me from really making the resume 'my own'_.
* **README.md**: This file right here. Markdown. I thought _people believe John_
* **resources.txt**: A stripped down version of <a href="http://georgeplaten.github.io/fe-p2/resources.html">resources.html</a>.
* and some custom images in the images directory.

My repository also includes:

* **.gitignore**: git file that helps stop me uploading windows Thumbs.db files and other things
* **js/jquery-ui.min.js**: for 'udacious' interactive layout manipulation (accordion effect)
* **css/jquery-ui.min.css**: required by jqueryui

### The process:
The resume has six distinct sections: work, education, projects, an interactive map, a header with biographical information and a footer with quick contact information.

1. All section draw their data from four JSON-like objects, containing work, biography, education and projects information. The objects also contain a method to write that data to the page.
The objects I created follow the names within the schema below exactly, but not the values. They were confirmed to be formatted correctly with <a href="http://jsonlint.com/" target="_blank">JSONlint.com</a>. There are some additions made to the object based on adding standard functionality such as alt attributes for images.
The **bolded** items show additions and / or deviations.
  <ul>
    <li>`bio` contains:
      <ul>
        <li>name : string</li>
        <li>role : string</li>
        <li>contacts : an object with
          <ul>
            <li>mobile: string</li>
            <li>email: string</li>
            <li>github: string</li>
            <li>twitter: string</li>
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
3. The resume includes an interactive map. I then found some functionality in the Google Maps online documentation and added some basic info the the place markers when clicked on.
4. My resume also includes `console.log()` information about click locations. I made a small easter egg addition to this function by adding some code to the helper.js file to hopefully help alleviate some boredom for the markers at Udacity.