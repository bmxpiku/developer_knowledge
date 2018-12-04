### Pay attention to:
 - Is there documentation?
 - whether in all obscure places there were relevant comments, written in the right way (not "what" the code does, only "why"),
 - are coding standards met,
 - is the principle of KISS fulfilled (let's take the development: Keep It Sophisticatedly Simple - simplify but not in a crude way) - especially in the context of code readability and naming of variables (if you sit 20 minutes over one function, something does not play ... unless you fell asleep),
 - is it done, as we do in other places well,
 - are unit tests added or updated,
 - are errors correctly logged,
 - whether the correct module import was ensured,
 - whether the proper handling of SQL transactions (rollback!) was ensured,
 - does the code meet the SOLID rules (after Robert C.Martin, I recommend you wygoogle'ować),
 - does the code meet the DRY rule (Do not Repeat Yourself),
 - what is the impact of changes on existing code
 - what is the generality of methods / reusability of the code
 - what is the future of the solution, but ... remember the principle of YAGNI (You Is not Gonna Need It - you will not need it),
 - security,
 - security,
 - and again security,
 - whether the correct error handling is ensured, and if the error occurs, the information from it is properly recorded in the logs,
 - whether the solution meets the relevant performance criteria.



#### [others](http://koscielski.ninja/code-review-zwrocic-uwage/)
