You have the following DB structure:

- users
  - id                             
  - username
  - email   
  - secret

- coding_dojos
  - id
  - name
  - date

- coding_dojos-users
  - user_id
  - coding_dojo_id


Create the appropriate classes with the following methods using TDD, WITH DATABASE:
* createUser(user: object): Promise<User>
* createDojo(dojo: object): Promise<Dojo>
* subscribeToDojo(user_id: int, dojo_id: int): Promise<void>
* deleteUser(user_id): Promise<void>
* unsubscribeFromDojo(user_id: int, dojo_id: int): Promise<void>
    
Create the appropriate classes with the following methods using TDD, WITHOUT DATABASE:
* createUser(user: object): Promise<User>
* createDojo(dojo: object): Promise<Dojo>
* subscribeToDojo(user_id: int, dojo_id: int): Promise<void>
* deleteUser(user_id): Promise<void>
* unsubscribeFromDojo(user_id: int, dojo_id: int): Promise<void>

Implement the following methods in the appropriate classes:
* saveUser
    * Validates the user object
        * Email validation
        * Secret validation (at least 6 chars, at least 1 symbol, 1 letter, 1 number)
        * Username validation (no special characters, no whitespaces)
    * Throw error or save the user
* saveDojo
    * Validates the dojo object
        * Date should be in the future
        * Name should not contain special characters (whitespaces allowed)
    * Throw error or save the dojo
* subscribe
    * Validates the objects
        * Dojo should be in the future
        * User should not be subscribed yet
        * User should not be subscribed to any other dojo
    * Subscribes or error
* unsubscribe
    * Validates the object
        * Dojo should be in the future
        * User should be subscribed
    * Unsubscribes or error

Implement the following endpoints and use supertest
* GET /api/dojo - Lists the dojos that will be held in the future
* GET /api/dojo/:id - Returns the dojo’s information with the given id and the participants
* POST /api/user - Registers a user
* POST /api/dojo/:id Registers the user to the Dojo


