#Extmark &mdash; Extendable Markup Language  
Extmark is the base of a markup language similar to [Markdown]()/[Textile](), with the exception that it is specifically design to be extended functionality-wise. Extmark has a base language that is required by all instances of Extmark; however as long as the base language is included, and no additional syntax is required, the functionality of Extmark can be extened to a limitless extent.

---

##Syntax  
The syntax used is very simplistic, it uses square brackets to access methods and pass arguments, followed by parentheses to define the source to be modified. The lanuage also supports variables through curly brackets followed by parentheses to define the variables value. Variables can be accessed via a carot(^) followed by the variable name. Here is an example of the above.  

```
    {my_variable}(This really long thing that I don't want to write everytime I want to say it)  
    [method arg arg etc.](The source to be modified, and ^my_variable)  
```

Here is an example of an Extmark in a realistic instance:  

###Extmark Code:  
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

###Output  
Hello **Richard**,  
  
We regret to inform you that your last payment from card ending in 1234 was declined. You currently owe **$12.00 USD**  
  
Failure to pay the $12.00 USD by 12/23/2050 will result in a cancellation of service.  
  
John Smith  
*Billing Support Advisor*  
  
1234 Random Blvd.  
Seminole, FL 33772  
Phone: 727-555-0000  