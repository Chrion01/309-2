For assignment-3 we have completed and implemented all functionalities that we planned.

User login credentials are stored in our database and user sessions are managed by express sessions.

Usernames are unique and is what is stored to each session to identify the user that is currently logged in.

Use the navigation bar at the top right corner to navigate to different features of our web application. 

Press How it works button on the Home tab for detailed instructions on how to use our web-application.

The Edit Custom Thesaurus tab to allows users to add or remove their own synonyms or antonym for a word.

The Use Thesaurus tab allows the user to find synonyms and antonyms based on the thesaurus provided by wordAPI or their own custom thesaurus based on the radio buttons.

When using the custom thesaurus, it will return synonyms/antonyms from both the standard WordApi and the user's own custom entries. However, the user is able to remove entries that was originally from the standard WordApi using the Edit Custom Thesaurus tab so when performing searches using the custom thesaurus, they are able to omit and delete words that they are previously not able to through only the standard thesaurus. 

Use logout button to return to the login page.

We used Heroku and mLab to deploy our web application, server and database online and to the public. 

The web application can be accessed online from anywhere using this link: https://tsm-custom-thesaurus.herokuapp.com

Below we will go over RESTful calls that can be made to our API.

Note that since our web application is catered towards users seeking customization and personlization, in order to use our API, the user must register for an account and be logged in to use all the RESTful calls except for login and register.


To login:

/POST https://tsm-custom-thesaurus.herokuapp.com/login

Using body:
{username: 'your username', password: 'your password'}


To logout:

/POST https://tsm-custom-thesaurus.herokuapp.com/logout


To register:

/POST https://tsm-custom-thesaurus.herokuapp.com/register

Using body:
{username: 'your username', password: 'your password'}


To get the username of the user that is currently logged in and holding the session:

/GET https://tsm-custom-thesaurus.herokuapp.com/welcome


To change the password:

/PUT https://tsm-custom-thesaurus.herokuapp.com/changepassword

Using body: {
    password: 'your new password'
}


To get all of your account's custom entries. This will include all words that the user modified using the custom thesaurus feature:

/GET https://tsm-custom-thesaurus.herokuapp.com/words


To get either all the synonyms or antonyms from the custom thesaurus for a specific word:

/GET https://tsm-custom-thesaurus.herokuapp.com/words/:word/:type

With :word being the specific word you want to look up and :type being either 'synonyms' or 'antonyms'.(No quotation marks in the URL)


To add a word to the custom thesaurus:

/POST https://tsm-custom-thesaurus.herokuapp.com/words

Using body:
{
    word: 'your word', 
    type: 'either synonyms or antonyms', 
    definition: ['your','desired', 'array', 'of', 'synonyms/antonyms']
}


To update the synonyms/antonyms list of a spesific entry:

/PUT https://tsm-custom-thesaurus.herokuapp.com/words/:word/:type

With :word being the specific word you want to update and :type being either 'synonyms' or 'antonyms'.(No quotation marks in the URL)
With body:
{ definition: ['your','desired', 'array', 'of', 'synonyms/antonyms'] }


To delete an entire word and all of its synonyms/antonyms from the custom thesaurus:

/DELETE https://tsm-custom-thesaurus.herokuapp.com/words/:word

With :word being the specific word you want to delete.

