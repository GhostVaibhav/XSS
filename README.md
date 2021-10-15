# XSS
Information Security Project (for College) demonstrating the 3 types of Cross Site Scripting vulnerabilities (Stored, Reflected, DOM)

**Mentor**: Professor Bhulakshmi Bonthu

**Team**:

    Vaibhav Sharma (20BKT0030)
    
    Krish G Jain (20BKT0050)
    
    Vijay Nikhil (20BKT0004)
    
**Technologies**:

  JavaScript - Core & JQuery on Front End, Node.js & Express.js on Back End
  
  EJS (Embedded JavaScript) templating engine
  
  HTML, Bootstrap
  
  Database: MongoDB
  

**Why is the site vulnerable?**

The vulnerability originates from the way we have used EJS.
For displaying submitting comments, we use <%- ... %> tags in EJS. Thus, Node simply does a text substitution. So any HTML tags are interpreted as HTML instead of plain text.

The vulnerability can be fixed if we replace those tags with:

<%= ... %>  (NOTICE THE '-' HYPHENE IS REPLACED BY '=' EQUAL TO)

This encodes the HTML tags, i.e., \<script\> becomes \&lt;script\&gt;
