# M183 Cross Site Scripting (XSS)

Cross-Site Scripting (XSS) attacks are a type of injection, in which malicious scripts are injected into otherwise benign and trusted websites. XSS attacks occur when an attacker uses a web application to send malicious code, generally in the form of a browser side script, to a different end user.

# WebGoat

A Demonstration of an XSS attack will be performed with the help of [WebGoat](https://owasp.org/www-project-webgoat/#:~:text=WebGoat%20is%20a%20deliberately%20insecure,and%20popular%20open%20source%20components.).

WebGoat is a deliberately insecure application that allows interested developers just like you to test vulnerabilities commonly found in Java-based applications that use common and popular open source components.

> To run WebGoat docker container: docker run -p 127.0.0.1:8080:8080 -p 127.0.0.1:9090:9090 -e TZ=Europe/Amsterdam webgoat/webgoat

WebGoat will be located at: http://127.0.0.1:8080/WebGoat





# How to prevent XSS attacks
Preventing cross-site scripting is trivial in some cases but can be much harder depending on the complexity of the application and the ways it handles user-controllable data.

In general, effectively preventing XSS vulnerabilities is likely to involve a combination of the following measures:

- Filter input on arrival. At the point where user input is received, filter as strictly as possible based on what is expected or valid input.
- Encode data on output. At the point where user-controllable data is output in HTTP responses, encode the output to prevent it from being interpreted as active content. Depending on the output context, this might require applying combinations of HTML, URL, JavaScript, and CSS encoding.
- Use appropriate response headers. To prevent XSS in HTTP responses that aren't intended to contain any HTML or JavaScript, you can use the Content-Type and X-Content-Type-Options headers to ensure that browsers interpret the responses in the way you intend.
- Content Security Policy. As a last line of defense, you can use Content Security Policy (CSP) to reduce the severity of any XSS vulnerabilities that still occur.

## What is "Escaping strings"?
Escaping a string means to reduce ambiguity in quotes (and other characters) used in that string. For instance, when you're defining a string, you typically surround it in either double quotes or single quotes:

> "Hello, World."

But what if the string had double quotes within it?

> "Hello "World.""

Now we have ambiguity - the software doesn't know where my string ends. one solution is to use single quotes around the string:

'Hello "World."'

Or I can escape my quotes:

> "Hello \"World.\""

Any quote that is preceded by a slash is escaped and understood to be part of the value of the string.

Character combinations consisting of a backslash (\) followed by a letter or by a combination of digits are called "escape sequences." To represent a newline character, single quotation mark, or certain other characters in a character constant, you must use escape sequences. An escape sequence is regarded as a single character and is therefore valid as a character constant.

# Reflextion

## Raphael

Der Einstieg in das Modul mit den OWASP Themen war spannend und auch breit in den Themen. Das Thema Cross Site Scrpiting und SQL-Injections gefiel mir besonder weil es direkt mit dem Modul 151 am morgen zusammenhängt. Zusammen mit Herr Achermann vertieften wir uns in diese Sicherheitsrisiken und bauten uns Fachwissen hierzu auf. Die Community Software WebGoat half uns visuell das XSS und ihre Problematik zu verstehen. Ich konnte die Sicherheitsthemen die wir in diesem Modul besprochen haben gleich im Modul 151 für ein Webshop Projekt verwenden und wusste dort becheid wenn es um das Sichern vor Fremdzugriffen oder Manipulation ging. Einige Sicherheitsrisiken waren ein Wenig zu Abstrakt für mich oder ich hatte noch keinen grossen Kontakt mit den Themen. Ich fand das Modul war gut abgerundet mit aktuellen Sicherheitsthemen.

## Oliver

Applikationssicherheit war schon immer ein interessantes Thema für mich. Es interessiert mich, was für Angriffsmöglichkeit es gibt und wie man seine Applikation Angriffssicher programmiert. Zusammen mit Herr Blaauw habe ich mich in das Thema Cross Site Scripting, auch als XSS bekannt, vertieft. Mit Hlife von einer Community Projekt names Webgoat konnten wir Cross Site Script Angriffe simulieren. Das hat sehr geholfen, denn in Wörtern ist es abstrakt und schwierig zu verstehen, um was es sich eigentlich handelt. Gelernt habe ich ebenfalls, was Escaping ist und wieso das gegen Cross Site Scripting schützt. Es hat mich sehr gefreut und das Modul fand ich sehr gut gestaltet
