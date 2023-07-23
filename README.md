# Pokemon_Microservice

Overview of the microservice

The microservice integrates with my partner’s Pokemon guessing game by providing the names of the characters for which images exist, a random name of a character for which an image exists, and the image of a character.  The microservice has a character name and character image (link) lookup such that if the request includes a character name, redirection to the image link occurs.  If the request is for “characters” then the names of all of the available characters (currently ~300) is returned.  If no special information is specified (no character name and not “characters”) then the name of a random character is returned.


Description of how to programmatically request data from the microservice

Three different types of calls corresponding to each of the 3 user stories are supported currently:
1.	townerc.pythonanywhere.com – This returns a random name of a Pokemon character for which an image link exists.  For example, a GET request to townerc.pythonanywhere.com might return the Pokemon character name "Cascoon" as that is one of the ~300 characters with images available.
 
2.	townerc.pythonanywhere.com/<name> – This redirects the user to the image of the Pokemon character.  For example, townerc.pythonanywhere.com/Cascoon redirects to imgix.ranker.com/.../cascoon-u3.jpg

3.	townerc.pythonanywhere.com/characters – This returns a list of the characters for which images exist.  For example: townerc.pythonanywhere.com/characters returns Bulbasaur, Ivysaur, ...


UML sequence diagram that clearly communicates how to programmatically request and programmatically receive data from the microservice you implemented; No obvious notational errors

user                         townerc.pythonanywhere.com

GET townerc.pythonanywhere.com/ -------->   

<---  Random Character Name 


GET townerc.pythonanywhere.com/<name> -->

<---  Redirect to image of character


GET townerc.pythonanywhere.com/characters

<---  Names of all characters