Download Link: https://assignmentchef.com/product/solved-web222-assignment4-practice-styling-elements-with-css
<br>
Objective:

Practice Styling elements with CSS, Updating the DOM with data &amp; responding to user events.

Specification (Part A):

For Part A, we will be creating a small demo app that works with “Pet” data, i.e., dogs, cats &amp; birds. This app will show all of the pets from a “petData” array of objects and allow the user to filter which pets they would like to see. This app must also be visually appealing, so we must update/override existing CSS to create a more customized experience for the user.

To begin, download the assignment4.zip file containing all of the files required for Assignment 4 from blackboard.

Uncompress the assignment4.zip file somewhere on your local machine. When you’re ready to begin editing the files, open the uncompressed folder (assignment4) and locate the directory “partA”. Open this directory using Visual Studio Code (https://code.visualstudio.com). You may test your html files in any modern browser (Chrome, Firefox, Safari, Internet Explorer, etc.):

<strong>Updating File: “main.html” </strong>

The main page of our app will be the “main.html” file. There is already some code there, but must configure it further to create some interactivity and personalization for the app

<ol>

 <li>Give your app a name by updating the &lt;title&gt;&lt;/title&gt; tag, i.e. “~ A4 Pets ~”</li>

 <li>Update the &lt;h1 class=”app-title”&gt;&lt;/h1&gt; element to match the name of your app. It currently states “App Title”, but this must be changed to something more appropriate (i.e. “~ Purfect Pets ~”)</li>

 <li>Update the “onclick” values <strong>all the &lt;a&gt; elements </strong>inside the top &lt;ul&gt; element to call appropriate filtering functions (to be written later). For example clicking “Dogs” should call a function that updates the table to <strong>only show Dogs </strong>(i.e., invokes the filterDogs() function – see below )</li>

 <li><strong> Update the &lt;footer&gt; element to show your full name (zero will be assigned for failure to do so). </strong></li>

</ol>

<strong>Updating File: “a4-main.js” </strong>

All of the JavaScript for the solution (except for the data) is located in the file “a4-main.js”. Inside this file, write a series of functions to render the data (“petData” located within js/data.js). You <strong>must not use innerHTML</strong> unless explicitly instructed to do so (there are two instances where it is necessary). The functions are follows:

<ol>

 <li>Function: <strong>loadTableWithFilters </strong></li>

</ol>

This function will take all of the data from the global “petData” array (located within js/data.js) and render it as rows within the &lt;tbody id=”main-table-body”&gt;&lt;/tbody&gt; element in the main.html file

It must use the global filter values, i.e.: <strong>filterType </strong>(possible values: “cat”, “dog”, “bird”, or “”), <strong>filterAgeMin </strong>(any positive number) and <strong>filterAgeMax </strong>(any positive number) to conditionally show rows depending on a pet’s <strong>type</strong>, or <strong>age </strong>values. For example, if the value of <strong>filterType </strong>is “cat”, the value of <strong>filterAgeMin </strong>is <strong>1 </strong>and the value of <strong>filterAgeMax </strong>is <strong>3 </strong>then only pets with <strong>type: “cat” </strong>who are between the age of <strong>1 </strong>and <strong>3 </strong>(exclusively) will be added as rows within the &lt;tbody id=”main-table-body”&gt;&lt;/tbody&gt; element.

Before any rows are added to the &lt;tbody id=”main-table-body”&gt;&lt;/tbody&gt; element however, it must be cleared of all existing data. <strong>This can be done using element.innerHTML = “”</strong>

Lastly, this function must be invoked inside window.onload to ensure that the &lt;tbody id=”main-table-body”&gt;&lt;/tbody&gt; element is initially populated with all of the pets inside the “petData” array.

As an example of how each new row must be rendered, consider the following example for <strong>Bella </strong>the dog:

<strong><u>Data: </u></strong>

image: { src: “https://zenit.senecac.on.ca/~tanvir.alam/shared/winter-2017/web222/assignment4/pets/Bella.jpg”, alt: “Bella”, width: 120, height: 160 },

name: “Bella”,

age: 0.5,

description: “&lt;span&gt;Bella&lt;/span&gt; is a bright young pup who loves being around other dogs and doesn’t mind the odd cat.&lt;br /&gt;Her &lt;span&gt;favourite treat&lt;/span&gt; is &lt;span&gt;bacon&lt;/span&gt; – anything &lt;span&gt;bacon&lt;/span&gt;.”,

type: “dog”

<strong><u>Rendered HTML (&lt;tr&gt;&lt;/tr&gt; element): </u></strong>

<strong>&lt;tr&gt; </strong>

&lt;td&gt;

<strong>         &lt;img </strong>src=”https://zenit.senecac.on.ca/~tanvir.alam/shared/winter-2017/web222/assignment4/pets/Bella.jpg” alt=”Bella” height=”160″ width=”120″<strong>&gt; </strong>

&lt;/td&gt;

&lt;td&gt;

<strong>         &lt;h4&gt;</strong>Bella<strong>&lt;/h4&gt; </strong>

<strong>         &lt;p&gt;&lt;span&gt;</strong>Bella<strong>&lt;/span&gt; </strong>is a bright young pup who loves being around other dogs and doesn’t mind the odd cat.<strong>&lt;br&gt;</strong>Her <strong>&lt;span&gt;</strong>favourite treat<strong>&lt;/span&gt;</strong>is <strong>&lt;span&gt;</strong>bacon<strong>&lt;/span&gt; </strong>– anything <strong>&lt;span&gt;</strong>bacon<strong>&lt;/span&gt;</strong>.<strong>&lt;/p&gt; </strong>

<strong>         &lt;span&gt;</strong>Age: 0.5 years old.<strong>&lt;/span&gt; </strong>

&lt;/td&gt;

<strong>&lt;/tr&gt;</strong>

<strong> </strong>

<strong>NOTE</strong>: You will notice that the <strong>description </strong>for all pets contains <strong>HTML </strong>code. For us to render this properly in our &lt;p&gt;&lt;/p&gt; element, <strong>we must use the innerHTML property </strong>( i.e.: <strong>p.innerHTML = petData[i].description </strong>)

<ol start="2">

 <li>Function: <strong>filterDog </strong></li>

</ol>

This function simply sets the global <strong>filterType </strong>variable to “<strong>dog</strong>” and invokes the <strong>loadTableWithFilters </strong>function again to refresh the table. This function <strong>must be invoked </strong>when the user <strong>clicks “Dogs”</strong>

<ol start="3">

 <li>Function: <strong>filterCat </strong></li>

</ol>

This function simply sets the global <strong>filterType </strong>variable to “<strong>cat</strong>” and invokes the <strong>loadTableWithFilters </strong>function again to refresh the table. This function <strong>must be invoked </strong>when the user <strong>clicks “Cats”</strong>

<ol start="4">

 <li>Function: <strong>filterBird </strong></li>

</ol>

This function simply sets the global <strong>filterType </strong>variable to “<strong>bird</strong>” and invokes the <strong>loadTableWithFilters </strong>function again to refresh the table. This function <strong>must be invoked </strong>when the user <strong>clicks “Birds”</strong>

<ol start="5">

 <li>Function: <strong>filter_zero_1 </strong></li>

</ol>

This function simply sets the global <strong>filterAgeMin </strong>variable to <strong>0</strong>, the <strong>filterAgeMax </strong>variable to <strong>1 </strong>and invokes the <strong>loadTableWithFilters </strong>function again to refresh the table. This function <strong>must be invoked </strong>when the user <strong>clicks “&lt; 1 year”</strong>

<ol start="6">

 <li>Function: <strong>filter_1_3 </strong></li>

</ol>

This function simply sets the global <strong>filterAgeMin </strong>variable to <strong>1</strong>, the <strong>filterAgeMax </strong>variable to <strong>3 </strong>and invokes the <strong>loadTableWithFilters </strong>function again to refresh the table. This function <strong>must be invoked </strong>when the user <strong>clicks “1 – 3 years”</strong>

<ol start="7">

 <li>Function: <strong>filter_4_plus </strong></li>

</ol>

This function simply sets the global <strong>filterAgeMin </strong>variable to <strong>4</strong>, the <strong>filterAgeMax </strong>variable to <strong>Number.MAX_VALUE </strong>and invokes the <strong>loadTableWithFilters </strong>function again to refresh the table. This function <strong>must be invoked </strong>when the user <strong>clicks “4+ years”</strong>

<ol start="8">

 <li>Function: <strong>filterAllPets </strong></li>

</ol>

This function simply sets the global <strong>filterType </strong>variable to <strong>“”</strong>, the <strong>filterAgeMin </strong>variable to <strong>0</strong>, the <strong>filterAgeMax </strong>variable to <strong>Number.MAX_VALUE </strong>and invokes the <strong>loadTableWithFilters </strong>function again to refresh the table. This function <strong>must be invoked </strong>when the user <strong>clicks “All Pets”</strong>

<strong>Updating File: “a4-main.css” – see: </strong><a href="https://zenit.senecac.on.ca/~tanvir.alam/shared/winter-2017/web222/assignment4/pets/css-sample.jpg">completed sample</a>

Now that the table is getting populated with our data and the filters are up and running, we need to make the app a little nicer to look at. This next step involves updating the CSS file “a4-css.css” to clean up the layout and add some colour and style:

<ol>

 <li><strong> Add a new font colour to the &lt;body&gt; element </strong></li>

 <li>Add a new background colour to the &lt;nav&gt; and &lt;footer&gt; elements</li>

 <li>Style the &lt;header&gt;&lt;/header&gt; element using at least <strong>2 </strong>properties</li>

 <li>Style the &lt;h1 class=”app-title”&gt;&lt;/h1&gt; using at least <strong>3 </strong>properties. One of these properties <strong>must </strong>be setting the font to a “web-font”, available on the Google Fonts CDN</li>

 <li>Style the &lt;div class=”main-table-container”&gt;&lt;/div&gt; using at least <strong>3 properties</strong>, two of which must be to ensure that it has:</li>

</ol>

<ul>

 <li style="list-style-type: none;">

  <ul>

   <li>a maximum height value</li>

   <li>a vertical scroll bar</li>

  </ul></li>

</ul>

<ul>

 <li></li>

 <li>This will allow our table to scroll, instead of taking up a ton of vertical space on the page.</li>

 <li></li>

</ul>

<ol start="6">

 <li>Add at least <strong>4 </strong>style properties to the &lt;th&gt;&lt;/th&gt; elements inside the &lt;table class=”main-table-top”&gt;&lt;/table&gt; element. This will ensure that the top (stationary) row of our table looks distinctives.</li>

 <li>Add at least <strong>4 </strong>style properties to the &lt;td&gt;&lt;/td&gt; elements inside the &lt;table class=”main-table”&gt;&lt;/table&gt; element. This will ensure that the cells within our main table have appropriate spacing and are styled to match the rest of the page.</li>

 <li>Add at least <strong>2 </strong>properties to all &lt;span&gt;&lt;/span&gt; elements that are used for the description of the pets. These &lt;span&gt;&lt;/span&gt; elements will be located inside &lt;p&gt;&lt;/p&gt; elements within the &lt;table class=”main-table”&gt;&lt;/table&gt; element. This will ensure that anytime a &lt;span&gt;&lt;/span&gt; element is used in the description of a pet, the text will be highlighted.</li>

 <li>Lastly, update the academic honesty statement at the top of the file with your name and the current date.</li>

</ol>

Specification (Part B):

For Part B, we will be creating and a new CSS file to be used in the CanadianPT.html file located within the PartB folder.

When you’re ready to begin editing the files, open the uncompressed folder (assignment4) and locate the directory “partB”. Open this directory using Visual Studio Code (https://code.visualstudio.com). You may test your html files in any modern browser (Chrome, Firefox, Safari, Internet Explorer, etc).

Please note: when developing your CSS, you <strong>must add comments (/* … */) </strong>to describe each of the selectors. For example, above the selector “<strong>.main-container nav</strong>”, include the comment <strong>/* Select all &lt;nav&gt; elements that are a child of an element with class “main-container” and adjust it’s size and position */</strong>.

Getting Started– <a href="https://zenit.senecac.on.ca/~tanvir.alam/shared/winter-2017/web222/assignment4/partB-samples/1.png">completed sample</a> 1.png

<ul>

 <li>locate the “<strong>css</strong>” directory and add the file “<strong>css</strong>”</li>

 <li>Open the file “<strong>html</strong>” for editing and add the <strong>&lt;link&gt; </strong>tag to include your new <strong>site.css </strong>file</li>

 <li>Open <strong>html </strong>in a web browser</li>

 <li>Open both “<strong>css</strong>” and “<strong>canadianPT.html</strong>” for editing/viewing</li>

</ul>

Step 1 – Styling the main containers – <a href="https://zenit.senecac.on.ca/~tanvir.alam/shared/winter-2017/web222/assignment4/partB-samples/2.png">completed sample</a> 2.png

<ul>

 <li>Notice how the page “<strong>html</strong>” is broken up into major sections: <strong>&lt;div class=”main-container”&gt;…&lt;/div&gt;</strong>, <strong>&lt;header&gt;…&lt;/header&gt;, &lt;nav&gt;…&lt;/nav&gt;, &lt;section class=”main”&gt;…&lt;/section&gt; </strong>and <strong>&lt;footer&gt;…&lt;/footer&gt; </strong></li>

 <li>We need to apply styles to these sections, so add the following CSS Selectors (in the file <strong>css</strong>) to your page. For each selector, use the suggested CSS Properties to achieve each design requirement. See the completed sample for reference</li>

</ul>




<table>

 <tbody>

  <tr>

   <td width="208"><strong>CSS Selector </strong></td>

   <td width="208"><strong>Design Requirement </strong></td>

   <td width="208"><strong>Suggested CSS Properties </strong></td>

  </tr>

  <tr>

   <td width="208"><strong>.main-container </strong></td>

   <td width="208">• Set the maximum width to 960 pixels• No top or bottom margins• Left and right margins must be “auto” </td>

   <td width="208">• max-width• margin </td>

  </tr>

  <tr>

   <td width="208"><strong>.main-container nav </strong></td>

   <td width="208">• Set the width to 30%• Element is positioned on the left side of the page </td>

   <td width="208">• width• float </td>

  </tr>

  <tr>

   <td width="208"><strong>.main-container .main </strong></td>

   <td width="208">• Set the width to 70%• Element is Positioned on the right side of the page </td>

   <td width="208">• width• float </td>

  </tr>

  <tr>

   <td width="208"><strong>.main-container header </strong></td>

   <td width="208">• Padding around the content must be 10 pixels• Background colour must be #eeeeee• There must be a solid bottom border 1 pixel thick, coloured #cccccc• Bottom margin must be 30 pixels </td>

   <td width="208">• padding• background-color• border-bottom• margin-bottom </td>

  </tr>

  <tr>

   <td width="208"><strong>.main-container header h1 </strong></td>

   <td width="208">• Set the width to 70%• The size of the font must be 24 pixels• Element is Positioned on the right side• The text is right-aligned• Top margin must be 10 pixels </td>

   <td width="208">• width• font-size• float• text-align• margin-top </td>

  </tr>

  <tr>

   <td width="208"><strong>.main-container footer </strong></td>

   <td width="208">• position the element beneath all floating elements (“clear” the element)• Padding around the top and bottom must be 20 pixels• Padding around the left and right must be 10 pixels• Background colour must be #eeeeee• There must be a solid top border 1 pixel thick, coloured #cccccc• The size of the font must be 13 pixels</td>

   <td width="208">• clear• padding• background-color• border-top• font-size </td>

  </tr>

 </tbody>

</table>

<ul>

 <li></li>

 <li>Step 2 – Styling the navigation and logo – <a href="https://zenit.senecac.on.ca/~tanvir.alam/shared/winter-2017/web222/assignment4/partB-samples/3.png">completed sample</a>png</li>

 <li>Now that the page is looking a little more organized, we want to update the “Canada” logo (flag &amp; name) as well as the side navigation to look a little cleaner. For each selector, use the suggested CSS Properties to achieve each design requirement. See the completed sample for reference</li>

</ul>

<table>

 <tbody>

  <tr>

   <td width="208"><strong>CSS Selector </strong></td>

   <td width="208"><strong>Design Requirement </strong></td>

   <td width="208"><strong>Suggested CSS Properties </strong></td>

  </tr>

  <tr>

   <td width="208"><strong>#logo </strong></td>

   <td width="208">• Set the width to 30%• The size of the font must be 25 pixels• The font must be bold </td>

   <td width="208">• width• font-size• font-weight </td>

  </tr>

  <tr>

   <td width="208"><strong>#logo img </strong></td>

   <td width="208">• The image must be 94 pixels wide• The image must be vertically positioned in the middle, relative to the “Canada” text </td>

   <td width="208">• width• vertical-align </td>

  </tr>

  <tr>

   <td width="208"><strong>nav ul </strong></td>

   <td width="208">• Do not show any bullets or numbers for the list </td>

   <td width="208">• list-style-type </td>

  </tr>

  <tr>

   <td width="208"><strong>nav ul a </strong></td>

   <td width="208">• render the link as a “block-level” element• remove the underline• Padding around the link must be 5 pixels </td>

   <td width="208">• display• text-decoration• padding </td>

  </tr>

 </tbody>

</table>




Step 3 – Styling the province containers – <a href="https://zenit.senecac.on.ca/~tanvir.alam/shared/winter-2017/web222/assignment4/partB-samples/4.png">completed sample 4.png</a> and <a href="https://zenit.senecac.on.ca/~tanvir.alam/shared/winter-2017/web222/assignment4/partB-samples/4-resized.png">4-resize.png</a>

<ul>

 <li>Everything is looking pretty good, but the page is very vertical. For a more modern design, we will render all of the provinces as “cards” and allow them to sit side-by-side horizontally. We also want to allow them to move onto the next line and render correctly if the user decides to resize the browser window. For each selector, use the suggested CSS Properties to achieve each design requirement. See the completed samples for reference</li>

</ul>

<table>

 <tbody>

  <tr>

   <td width="208"><strong>CSS Selector </strong></td>

   <td width="208"><strong>Design Requirement </strong></td>

   <td width="208"><strong>Suggested CSS Properties </strong></td>

  </tr>

  <tr>

   <td width="208"><strong>div.province </strong></td>

   <td width="208">• Set the width to 30%• Each new element is positioned to the right of the previous element, horizontally (<strong>hint</strong>: float:<strong>left</strong>)• The margin around the element must be 8 pixels• The height of the element must be 310 pixels </td>

   <td width="208">• width• float• margin• height </td>

  </tr>

  <tr>

   <td width="208"><strong>div.province .description </strong></td>

   <td width="208">• The element must not be any higher than 165 pixels• Only If the content goes beyond 165 pixels high, show a scroll bar• If the content does not fit in the container horizontally, hide the scrollbar• The top and bottom margins must be 8 pixels </td>

   <td width="208">• max-height• overflow-y• overflow-x• margin </td>

  </tr>

  <tr>

   <td width="208"><strong>div.province a </strong></td>

   <td width="208">• render the link as a “block-level” element• position the text in the middle of the element (horizontally)• set the colour of the background to #555555• Set the colour of the text to #eeeeee• remove the underline• Padding around the link must be 5 pixels </td>

   <td width="208">• display• text-align• background-color• color• text-decoration• padding </td>

  </tr>

  <tr>

   <td width="208"><strong>img.flag </strong></td>

   <td width="208">• set the width to be 100% of the parent </td>

   <td width="208">• width </td>

  </tr>

 </tbody>

</table>







<ul>

 <li>add the following declaration at the top of your site.css file:</li>

</ul>

<strong>/********************************************************************************* </strong>

<strong>* </strong>

<strong>* WEB222 – Assignment #4b </strong>

<strong>* </strong>

<strong>* I declare that this assignment is my own work in accordance with Seneca </strong>

<strong>* Academic Policy. No part of this assignment has been copied manually or </strong>

<strong>* electronically from any other source (including web sites) or distributed to </strong>

<strong>* other students. </strong>

<strong>* </strong>

<strong>* Name: ______________________ Student ID: ______________ Date: ________________ </strong>

<strong>* </strong>

<strong>********************************************************************************/</strong>

<strong> </strong>

Other Requirements

<ul>

 <li>Each HTML page in Part A &amp; B <strong>MUST PASS (no errors) </strong>the <strong>W3C’s HTML Validation</strong>: https://validator.w3.org/</li>

</ul>

All CSS used in the assignment <strong>MUST PASS (no errors) </strong>the <strong>W3C CSS Validation</strong>: https://jigsaw.w3.org/css-validator