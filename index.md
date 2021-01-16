## Welcome to the 7th episode of my series **Code for Security**.  

<div align="center"> <img src="cover.png"/> </div>  
  
When the 7th episode shows up, the Legendary man, Hyde4thHeaven is also known as "the Man with Seven Episodes", due to the seven episode engraved on his wall patterned after the shape of the Big Dipper. Hyde4thHeaven's famous catchphrase just prior to an vulnerability's death is "You are already dead!" (お前はもう死んでいる, Omae wa mō shindeiru).  
  
To reduce the risk of cross-site scripting attacks, templating systems, such as Twig, Django, Smarty, Groovy's template engine, allow configuration of automatic variable escaping before rendering templates. When escape occurs, characters that make sense to the browser (eg: <a>) will be transformed/replaced with escaped/sanitized values (eg: & lt;a& gt; ).  
  
Auto-escaping is not a magic feature to annihilate all cross-site scripting attacks, it depends on the strategy applied and the context, for example a "_html auto-escaping_" strategy (which only transforms html characters into html entities) will not be relevant when variables are used in a html attribute because ':' character is not escaped and thus an attack as below is possible:  
  
> \<a href="{{ myLink }}">link</a> // myLink = javascript:alert(document.cookie)  
> \<a href="javascript:alert(document.cookie)">link</a> // JS injection (XSS attack)  
  
### Ask Yourself Whether  
Templates are used to render web content and  
- dynamic variables in templates come from untrusted locations or are user-controlled inputs  
- there is no local mechanism in place to sanitize or validate the inputs.  
  
There is a risk if you answered yes to any of those questions.  
  
### Recommended Secure Coding Practices  
Enable auto-escaping by default and continue to review the use of inputs in order to be sure that the chosen auto-escaping strategy is the right one.
  
## Sensitive Code Example
<div align="center"> <img src="false.png"/> </div> 
    
## Solution
<div align="center"> <img src="true.png"/> </div> 
   
**Another secure function is done!** Secured coding is just a flipped hand when you know the hint!

Let's hunt more vulnerable code to make **Code for Security** next episode. Stay tuned!  
  
**#(autoescape=True) #Code4Sec**  
  
**Credit/Ref:**  
- OWASP Cheat Sheet - XSS Prevention Cheat Sheet
- OWASP Top 10 2017 Category A7 - Cross-Site Scripting (XSS)
- MITRE, CWE-79 - Improper Neutralization of Input During Web Page Generation ('Cross-site Scripting')
- MITRE, CWE-80 - Improper Neutralization of Script-Related HTML Tags in a Web Page (Basic XSS)
- MITRE, CWE-83 - Improper Neutralization of Script in Attributes in a Web Page
- MITRE, CWE-84 - Improper Neutralization of Encoded URI Schemes in a Web Page
   
______________________________
<table border="0">
 <tr>
   <td> <h3><i>Although my profile picture is quiet, but the real me can make some noise.</i></h3>
      <hr>
      <b><font color="Blue"> Author: Vuttawat Uyanont </font></b>  <br>
      <font color="grey"><i>Sexiest former engineer & banker who interested in Tech, Sake, and Beer.</i></font>  <br>
      <b>Studying:</b> Master Computer Science in Cybersecurity Management at Mahanakorn University.  <br> </td>  
   <td><img src="Author.png" width="150"/></td>  
 </tr>
</table>
  
