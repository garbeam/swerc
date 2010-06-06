The Rc Template Language
========================

Implemented by Kris, thanks!

Basic syntax:

* Lines starting with % are executed as rc commands, the resulting output is inserted in the document.
* use %{ and %} to delimit multi line sections of rc code (note the lack of space between % and { or }!
* To 'inline' the value of an environment variable use `%($my_var%)`

That is basically it!

For further documentation on rc see:

* [The rc(1) man page for Plan 9](http://man.cat-v.org/plan_9/1/rc).
* [The rc shell paper by Tom Duff](http://rc.cat-v.org).


Examples
--------

Loops

    <ul>
    % for(i in a b c) {
    %   echo '<li>'$i'</li>'
    % }
    </uL>
 
Is equivalent to: 

    <ul>
    % for(i in a b c) {
    <li>%($i%)</li>
    % }
    </uL>

and results in this output:

    <ul>
    <li>a</li>
    <li>b</li>
    <li>c</li>
    </ul>
