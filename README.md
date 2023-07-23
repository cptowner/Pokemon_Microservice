# Pokemon_Microservice

Overview of the microservice

The microservice integrates with my partner’s Pokemon guessing game by providing the names of the characters for which images exist, a random name of a character for which an image exists, and the image of a character.  The microservice has a character name and character image (link) lookup such that if the request includes a character name, redirection to the image link occurs.  If the request is for “characters” then the names of all of the available characters (currently ~300) is returned.  If no special information is specified (no character name and not “characters”) then the name of a random character is returned.


Description of how to programmatically request data from the microservice

Three different types of calls corresponding to each of the 3 user stories are supported currently:
1.	townerc.pythonanywhere.com – This returns a random name of a Pokemon character for which an image link exists.  For example, a GET request to townerc.pythonanywhere.com might return the Pokemon character name "Cascoon" as that is one of the ~300 characters with images available.
 
2.	townerc.pythonanywhere.com/<name> – This redirects the user to the image of the Pokemon character.  For example, townerc.pythonanywhere.com/Cascoon redirects to imgix.ranker.com/.../cascoon-u3.jpg

3.	townerc.pythonanywhere.com/characters – This returns a list of the characters for which images exist.  For example: townerc.pythonanywhere.com/characters returns Bulbasaur, Ivysaur, ...


UML sequence diagram that clearly communicates how to programmatically request and programmatically receive data from the microservice you implemented; No obvious notational errors

<img width="534" alt="image" src="https://github.com/cptowner/Pokemon_Microservice/assets/3808424/8535720b-49c6-47a6-92b5-8685aeafc205">


https://sequencediagram.org/
title Pokemon Microservice

User->Microservice:GET request to townerc.pythonanywhere.com
User<--Microservice: HTTP response body includes name \nof Pokemon character for which an \nimage exists
User->Microservice:GET request to townerc.pythonanywhere.com/<name>
User<--Microservice: HTTP redirect to image source of the character
User->Microservice:GET request to townerc.pythonanywhere.com/characters
User<--Microservice: HTTP response body includes names \nof all Pokemon characters for which an \nimage exists
