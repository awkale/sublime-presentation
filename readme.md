# Sublimetext or: How I Learned to Stop Worrying and Love this Texteditor.

## Elevator Pitch
* multiple cursors
* vintage mode
* lightening fast
* for cool kids
* command palette
* plugins

## Getting Started
### Color Schemes
### Default Settings
* all changes reset on update
* use 'settings - user'

### Open from Terminal
command to create symbolic link
```
sudo ln -s "/Applications/Sublime Text 2.app/Contents/ShareSupport/bin/subl" /bin/subl
```
command to open all files in folder
```
subl .
```

### Multiple Cursors
* splitting the selection into lines
> ⌘+shift+L
* quick add next
> ⌘+D
* selects all matching occurrences
> ⌘+⋀+G
* column select
> ⌥+cursor
* incremental find
> ⌘+I

### Command Palette
* bring up command palette
> ⌘+shift+P
* e.g. change syntax quickly; plus many more quick changes
* allows fuzzy search
* goodbye mouse!
* less memorizing of shortcuts

### Instant File Changing
* goto anything
> ⌘+P
* fuzzy search

### Symbols
* open symbols
> user+R
* jumps to items on page
* merge instant file change and symbols
> ⌘+P ... @....

### Key Bindings
* customize your own keyboard shortcuts
* use 'keybindings user'
* 'super' = user

### Package Control
* a MUST have
* The Sublime Text package manager that makes it exceedingly simple to find, install and keep packages up-to-date.
* installation Sublime Text 2
  1.  open console
> ⋀+`
  2. paste and run code:

```
import urllib2,os,hashlib; h = '7183a2d3e96f11eeadd761d777e62404' + 'e330c659d4bb41d3bdf022e94cab3cd0'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); os.makedirs( ipp ) if not os.path.exists(ipp) else None; urllib2.install_opener( urllib2.build_opener( urllib2.ProxyHandler()) ); by = urllib2.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); open( os.path.join( ipp, pf), 'wb' ).write(by) if dh == h else None; print('Error validating download (got %s instead of %s), please try manual install' % (dh, h) if dh != h else 'Please restart Sublime Text to finish installation')
```

## Snippets
### Using Snippets
* via command palette
> ⌘+shift+P
* via tab trigger

### Creating Snippets
* via menu
> Tools > New Snippet

```
<snippet>
	<content><![CDATA[
Hello, ${1:this} is a ${2:snippet}.
]]></content>
	<!-- Optional: Set a tabTrigger to define how to trigger the snippet -->
	<!-- <tabTrigger>hello</tabTrigger> -->
	<!-- Optional: Set a scope to limit where the snippet will trigger -->
	<!-- <scope>source.python</scope> -->
</snippet>
```
* Save to User folder
> hello.sublime-snippet
* sub folder makes it syntax specific

```
<snippet>
	<content><![CDATA[
Hello, ${1:this} is a ${2:snippet}.
/*${1:stop point}*/
]]></content>
	<!-- Optional: Set a tabTrigger to define how to trigger the snippet -->
	<tabTrigger>hello</tabTrigger>
	<!-- Optional: Set a scope to limit where the snippet will trigger -->
	<!-- <scope>source.python</scope> -->
</snippet>
```

## Essential Plugins
### Emmet
* a plugin for many popular text editors which greatly improves HTML & CSS workflow

* Here’s an example: this abbreviation
```
#page>div.logo+ul#navigation>li*5>a{Item $}
```
* can be transformed into
```
<div id="page">
    <div class="logo"></div>
    <ul id="navigation">
        <li><a href="">Item 1</a></li>
        <li><a href="">Item 2</a></li>
        <li><a href="">Item 3</a></li>
        <li><a href="">Item 4</a></li>
        <li><a href="">Item 5</a></li>
    </ul>
</div>
```

### Theme - Soda
* Dark and light custom UI themes for Sublime Text

### SublimeLinter
* Interactive code linting framework for Sublime Text

### SidebarEnhancements
* Enhancements to Sublime Text sidebar. Files and folders.

### HTML5
* HTML5 bundle for Sublime Text

### BracketHighlighter
* Bracket and tag highlighter for Sublime Text

### Alignment
* Easy alignment of multiple selections and multi-line selections

## Tips, Techniques and Modifications
### Regular Expressions
* turn on regex
> ⌥+⌘+ R or first icon in find palette
* some regex  examples

  > `.` any character

  > `+` one or more of the preceding character

* e.g.
  > `<h2>.+</h2>` finds all h2 with any text

  > `(?<=<h2>).+(?<=</h2>)` finds all h2 with any text but ignores <h2>

### Vintage Mode
* takes time learn but powerful
* must be turned on
> `"ignored_packages": []`

### Quicker Stylesheet References
* copy path via command palette
  > ⌘+shift+P

  > File: Copy Path from Project
  > File: Copy as Tag style

### Joining Lines
* good for making arrays

### All About Projects
* have multiple folders in the settings array
* can exclude files, folders
> `"file_exclude_patterns": ["*.css"]`
> `"folder_exclude_patterns": ["*.css"]`
* switch project
> ⌘+⋀+P
* have project specific settings
> ```
"settings":
    {
      "tab_size": 10
    }
```

### Configuring and Mastering Split Windows
* create splits
> ⌘+⌥+2
* move file via menu or shortcut
> ⋀+shift+2
* shift focus
> ⋀+2
* can use keybindings for dimension of splits
