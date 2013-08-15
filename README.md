#Extmark &mdash; Extendable Markup Language  
Extmark is the base of a markup language similar to [Markdown]()/[Textile](), with the exception that it is specifically design to be extended functionality-wise. Extmark has a base language that is required by all instances of Extmark; however as long as the base language is included, and no additional syntax is required, the functionality of Extmark can be extened to a limitless extent.

---

##Syntax  
The syntax used is very simplistic, it uses square brackets to access methods and pass arguments, followed by parentheses to define the source text to be modified. The lanuage also supports variables through curly brackets followed by parentheses to define the variables value. Variables can be accessed via a carot(^) followed by the variable name. Additionally, the language supports block comments (via `/**/`) for personal notes. Here is an example of the above.  

**Important:** Method and variable brackets ALWAYS require a minimum of a method/variable name, and source text. All method arguments should be treated as optional in the code.

```
/* Mock Example */
{my_variable}(This really long thing that I don't want to write everytime I want to say it)  
[method arg1 arg2 etc.](The source to be modified, and ^my_variable)  

/* Context Example */
{username}(this_awesome_username)
My username is [code](^username)
```

The above context example would output: `My username is this_awesome_username`

####Advanced Syntax

Extmark's syntax interpreter, by default, takes the source text and imports it as a double quoted string. This functionality can be overridden by the writer (by sorrounding the source text in single/double quotes), or single/double quoted strings can be forced by methods. This is useful for un-escaping strings and pre-formated strings. The syntax is also designed to support objects (via a colon). This is particularly useful for preloading variables for use by writers, and sorting methods into categories, like so:

```
/* Mock Example */
[myClass:myMethod arg1 arg2 etc.](myClass:^myvariable)

/* Context Example */
hello my name is [user:name](%2, %1), and I enjoy [foods:fav](%1).
```

Here is an example of an Extmark in a realistic instance:  

####Extmark Code:  
```
Hello [font bold](^user_fname),  

We regret to inform you that your last payment from card ending in ^card_num was declined. You currently owe [font bold]($^balance_due USD).  

Failure to pay the $^balance_due USD by ^exp_date will result in a cancellation of service.  

^signature  

{user_fname}(Richard)  
{card_num}(1234)  
{balance_due}([math](6*2).00)  
{exp_date}(12/23/2050)  
{signature}(John Smith  
[font italic](Billing Support Advisor)  

1234 Random Blvd.  
Seminole, FL 33772  
Phone: 727-555-0000)  
```

####Output  
> Hello **Richard**,  
>   
> We regret to inform you that your last payment from card ending in 1234 was declined. You currently owe **$12.00 USD**  
>   
> Failure to pay the $12.00 USD by 12/23/2050 will result in a cancellation of service.  
>   
> John Smith  
> *Billing Support Advisor*  
>   
> 1234 Random Blvd.  
> Seminole, FL 33772  
> Phone: 727-555-0000  

##Supported Functionality








[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/ProjectCleverWeb/Extmark/trend.png)](https://bitdeli.com/free "Bitdeli Badge")



[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/ProjectCleverWeb/extmark/trend.png)](https://bitdeli.com/free "Bitdeli Badge")

