# SpringProject
## Functional Requirements for a Translation Website

There are two roles: user and administrator

### As a user, I can...

#### Search for words and phrases to translate
- I can enter words and phrases in different languages
- I can choose the language I want to translate from and to
- I can see the translation results in a convenient format

#### Access various dictionaries and information resources
- I can search for words and phrases in dictionaries
- I can read definitions, synonyms, and usage examples for words
- I can access other information resources, such as encyclopedias and text translations

#### Customize my settings
- I can choose my default language
- I can set the format for displaying translation results
- I can save my translations for later use

#### Communicate with other users
- I can comment on and rate other users' translations
- I can ask questions and get answers from other users
- I can participate in forums and discussion groups

### As an administrator, I can...

#### Manage the database of words and translations
- I can add, edit, and delete words and translations
- I can import and export data
- I can create and manage dictionaries

#### Manage users
- I can block/warn users
- I can assign roles and permissions to users
- I can track user activity

#### Configure the website
- I can change the website design
- I can add new features
- I can configure SEO settings

#### Monitor website performance
- I can view usage statistics
- I can track errors and problems
- I can optimize website performance

### General Requirements
- The website should be easy to use and navigate
- The website should be accessible to users of all skill levels
- The website should be reliable and secure
- The website should comply with modern web standards
- 
### Additional Requirements
- Ability to translate image text
- Ability to voice input and output
- Ability to translate in real time
- Ability to use the website on mobile devices



## System Behavior Description
### For User or Administrator
#### 1. Registration:

- Action:
User or administrator navigates to the registration page.
User or administrator enters required information, such as name, email address, and password.
User or administrator submits the registration form.

- Result:
System validates the entered information.
If the information is valid, the system creates a new user account and sends a confirmation email to the user's registered email address.
If the information is invalid, the system displays an error message indicating the errors.
Once the user confirms their email address, their account is activated.
#### 2. Login:

- Action:
User or administrator navigates to the login page.
User or administrator enters their registered email address and password.
User or administrator clicks the "Login" button.

- Result:
System validates the entered credentials.
If the credentials are valid, the system logs the user in and redirects them to the home page.
If the credentials are invalid, the system displays an error message indicating the invalid credentials.
#### 3. Forgot Password:

- Action:
User clicks on the "Forgot Password" link on the login page.
User enters their registered email address.
User clicks the "Reset Password" button.

- Result:
System checks if the entered email address is associated with an existing account.
If the email address is valid, the system sends a password reset link to the user's registered email address.
User clicks on the password reset link and enters a new password.
User clicks the "Reset Password" button.
System resets the user's password and sends a confirmation email to the user.
#### 4. Update Profile:

- Action:
User or administrator logs in to their account.
User or administrator navigates to their profile page.
User or administrator edits their profile information, such as name, email address, or password.
User or administrator clicks the "Save Changes" button.

- Result:
System validates the updated information.
If the information is valid, the system updates the user's profile and displays a success message.
If the information is invalid, the system displays an error message indicating the errors.
#### 5. Logout:

- Action:
User or administrator clicks the "Logout" button.

- Result:
System logs the user out of their account and redirects them to the login page.

### For User
#### 1. Translating words:

- Action:
User enters the word or phrase they want to translate into the input field.
User selects the language they want to translate from and to.
User clicks the "Translate" button.

- Result:
System sends a request to the translation server.
Translation server finds the translation of the entered word or phrase.
System displays the translation to the user.
#### 2. Suggesting corrections to the translation:

- Action:
User sees the translation of a word or phrase and believes it is incorrect.
User clicks the "Suggest Correction" button.
User enters their suggested correction for the translation.
User clicks the "Submit" button.

- Result:
System sends the user's suggested correction to the moderator team.
Moderator team reviews the suggested correction and decides whether to accept it.
If the suggested correction is accepted, the system updates the translation.
#### 3. Viewing translation history:

- Action:
User clicks the "Translation History" button.

- Result:
System displays a list of the user's previous translations.
User can click on any translation to view its details.
#### 4. Changing language settings:

- Action:
User clicks the "Settings" button.
User selects their default language.
User clicks the "Save" button.

- Result:
System sets the selected language as the default for translations.

#### 5. Providing feedback:
- Action:
User clicks the "Feedback" button.
User enters their feedback about the system.
User clicks the "Submit" button.

- Result:
System sends the user's feedback to the development team.
Development team reviews the user's feedback and uses it to improve the system.

### For Administrator
#### 1. Adding new word translations:

- Action:
Administrator clicks the "Add Translation" button.
Administrator enters the word or phrase to translate.
Administrator selects the language they want to translate from and to.
Administrator enters the translation of the word or phrase.
Administrator clicks the "Save" button.

- Result:
System adds the new translation to the database.
#### 2. Editing existing word translations:

- Action:
Administrator clicks the "Translations" button.
Administrator selects the word or phrase to edit.
Administrator edits the translation of the word or phrase.
Administrator clicks the "Save" button.

- Result:
System updates the translation in the database.
#### 3. Deleting word translations:
- Action:
Administrator clicks the "Translations" button.
Administrator selects the word or phrase to delete.
Administrator clicks the "Delete" button.

- Result:
System deletes the translation from the database.
#### 4. Adding new dictionaries:

- Action:
Administrator clicks the "Dictionaries" button.
Administrator clicks the "Add Dictionary" button.
Administrator enters the name of the dictionary.
Administrator selects the language of the dictionary.
Administrator clicks the "Save" button.

- Result:
System adds the new dictionary to the database.
#### 5. Editing existing dictionaries:

- Action:
Administrator clicks the "Dictionaries" button.
Administrator selects the dictionary to edit.
Administrator edits the name of the dictionary or the language of the dictionary.
Administrator clicks the "Save" button.

- Result:
System updates the dictionary in the database.
#### 6. Deleting dictionaries:

- Action:
Administrator clicks the "Dictionaries" button.
Administrator selects the dictionary to delete.
Administrator clicks the "Delete" button.

- Result:
System deletes the dictionary from the database.
#### 7. Managing users:
- Action:
Administrator clicks the "Users" button.
Administrator can add, edit, or delete users.
Administrator can assign roles and permissions to users.

- Result:
System manages users according to the administrator's actions.
#### 8. Viewing system logs:
- Action:
Administrator clicks the "Logs" button.

- Result:
System displays the system logs to the administrator.


## REST API Endpoints
### For User or Administrator
#### 1. Registration
- Method: POST
- Endpoint: /registration
- Parameters:
-- firstname: first name (required)
-- lastname: last name (required)
-- email: email address (required, unique)
-- password: password (required)
#### 2. Login
- Method: POST
- Endpoint: /login
- Parameters:
-- email: email address (required)
-- password: password (required)
#### 3. Forgot Password
- Method: POST
- Endpoint: /forgot-password
- Parameters:
-- email: email address (required)
#### 4. Update Profile
- Method: PUT
- Endpoint: /users/{user_id}
- Parameters:
-- user_id: ID of the user to update (required)
-- firstname: first name (optional)
-- lastname: last name (optional)
-- email: email address (optional)
-- password: password (optional)

### For User
### 5. View Another User Information
- Method: GET
- Endpoint: /users/{user_id}
- Parameters:
-- user_id: ID of the user to get information for (required)
#### 6. Translate Text
- Method: POST
- Endpoint: /translate-
- Parameters:
-- text: Text to translate (required)
-- from_language: Language to translate from (required)
-- to_language: Language to translate to (required)
#### 7. Suggest Translation Correction
- Method: POST
- Endpoint: /translations/{translation_id}/corrections
- Parameters:
-- translation_id: ID of the translation to suggest a correction for (required)
-- suggested_translation: Suggested correction for the translation (required)
#### 8. Get Translation History
- Method: GET
- Endpoint: /users/{user_id}/translations
- Parameters:
-- user_id: ID of the user to get translation history for (required)
#### 9. Change Language Settings
- Method: PUT
- Endpoint: /users/{user_id}/settings
- Parameters:
-- user_id: ID of the user to change language settings for (required)
-- default_language: User's default language (required)
#### 10. Provide Feedback
- Method: POST
- Endpoint: /feedback
- Parameters:
-- feedback: User's feedback (required)

### For Administrator
#### 1. Add New Word Translation
- Method: POST
- Endpoint: /translations
-  Parameters:
-- word: Word to translate (required)
-- from_language: Language to translate from (required)
-- to_language: Language to translate to (required)
-- translation: Translation of the word (required)
#### 2. Edit Existing Word Translation
- Method: PUT
- Endpoint: /translations/{translation_id}
- Parameters:
-- translation_id: ID of the translation to edit (required)
-- word: Word to translate (optional)
-- from_language: Language to translate from (optional)
-- to_language: Language to translate to (optional)
-- translation: Translation of the word (optional)
#### 3. Delete Word Translation
- Method: DELETE
- Endpoint: /translations/{translation_id}
- Parameters:
-- translation_id: ID of the translation to delete (required)
#### 4. Add New Dictionary
- Method: POST
- Endpoint: /dictionaries
- Parameters:
name: Name of the dictionary (required)
language: Language of the dictionary (required)
#### 5. Edit Existing Dictionary
- Method: PUT
- Endpoint: /dictionaries/{dictionary_id}
- Parameters:
--dictionary_id: ID of the dictionary to edit (required)
--name: Name of the dictionary (optional)
