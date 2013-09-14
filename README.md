ConstellationJS
================

An MIT Licensed node map generator and (soon to be) animated browser using RaphaelJS. 

Created by Garet Claborn and donated by Approach Foundation, LLC. 

approachfoundation.com

=================

This project is still in what you might be kind enough to call pre-alpha. It's "pretty cool" but not much else.

Well, I say that but you -can- manually do a heck of a lot with this little bitty. 

- Style a map with CSS, 
- have nodes shoot events
- talk to nodes and animate them on your own

Wait stop the presses.

This readme is pretty much over. We need to animate this thing and make it browseable. 
Also there's probably a ton of optimization that need to be found.
Also also, I need to fix the jQuery wrapping and class reflection. Derp.

Please help out if you can, I'll help you integrate this thing into whatever if you do!

I'm incorporating it into a CMS, report generator, activity monitor and event viewing tool.
Also trying to make a data modeler next.

Oh but I'll still put the base stuff below =)






================
BASIC USAGE
================

In a jQuery enabled JavaScript file OR
With your own "Document Ready" function OR
After your Stage element is surely defined in the body.

`$(function()
{    
  MyMap=new NodeMap('http://service.approachfoundation.org/Treedata.php'); 
});`

Next you will need an HTML file with and appropriate place for a Raphael paper to exist. Give this HTML element _id="Stage"_ or alter constellation.js call.init() function

Later I will add support for the syntax
_$(element).Constellation.call.init(webservice);_



`    <body bgcolor="#000000" style="background-color: #000;">`  
`        <div id="Stage" style="background-color: #888; height: 100%"><div>`  
`    </body>`




================
AJAX REQUIREMENTS
================

The AJAX you call needs to find a certain JSON format.
This is that format. You can host these on a CDN or have a web service give them to you.
I suggest doing both! Have the web service update the CDN as well.

[
 {
  "id":'anyval',
  "value":"(string)",
  "links":[],
 },
 {
  "id":'anyval2',
  "value":"(string)",
  "links":[],
 },
]

The "links[]" array Follows this same format. Feel free to have complex JSON objects for values or add other properties. You'll just need some minor tweaks to the ReceiveNodes function to tell Constellation what visual to put for your node.
