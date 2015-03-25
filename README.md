## Angular JS Markdown Editor / Preview

This directive is a Markdown editor and separate preview element. They can therefore be used independently. 

This uses PageDown for the conversion and sanitisation of the Markdown to HTML (i.e. the Preview element).

This uses Bootstrap-Markdown (http://toopay.github.io/bootstrap-markdown/) for the editor. The preview button has been disabled, to allow live-preview. 

Currently, the pagedown and bootstrap-markdown libraries are included, but will be replaced with Bower in a later version.

Usage is pretty trivial. It requires

- Add the dependency to the ['codemwnci.markdown-edit-preview'] module
- Angular JS (obviously)
- JQuery (for the editor to work)  **note: this must be defined first in the script list for the buttons to display**
- Pagedown (the Markdown previewer used by StackExchange, and many other sites)
- Bootstrap-Markdown
- Bootstrap 3 css (for the markdown editor to work)

### Example

See the index.html file to see a fully working example, with the required scripts in the head.

The first example turns a normal textarea, which is bound to the `mydata` angular scope variable, into a Markdown editor. The second line then binds to this editor and produces a live preview. 

    <textarea ng-model='mydata' markdownedit></textarea>
    <markdown bind-from='mydata'></markdown>

The second example show how you can just do a preview of markdown data already available. So, not Live Preview this time, but a Markdown render. It displays the rendered markdown that is stored in a scope variable called `myMD`

    <markdown bind-from='myMD'></markdown>

Further customisation of the editor is also possible. To change which buttons are hidden, it is possible to pass in a list of buttons names to the `markdown-hidden-buttons` attribute. Example three shows the removal of the Code and Quote buttons.

  	<textarea ng-model="mydata" markdownedit markdown-hidden-buttons="cmdCode,cmdQuote"></textarea>
	<markdown bind-from="mydata"></markdown>  		

The name of the buttons are as follows
- Bold = cmdBold 
- Italic = cmdItalic
- Heading = cmdHeading
- URL/Link = cmdUrl
- Image = cmdImage
- Unordered List = cmdList
- Ordered List = cmdList0
- Code = cmdCode
- Quote = cmdQuote
- Equation = cmdEquation
