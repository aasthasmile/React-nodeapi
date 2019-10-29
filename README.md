# React-nodeapi


Understanding of the React packages :

1. express-validator: https://express-validator.github.io/docs/
It is a validator of the input elements in the api e.g. JSON Schema Validator, Custom error messages(length or max characters in a string),Sanitization methods( string notEmpty() or trim() or HTML escape() or Email isEmail() ) and Wildcards Verification.

    //Verification consist of error message chaining for password.
     req.check('password')
	        .isLength({ min: 6 })
	        .withMessage('Password must contain at least 6 characters') //if length is less than 6 
	        .matches(/\d/)
	        .withMessage('Password must contain a number');//if password doesnot have atleast one number 

2. Virtual Field (Password)
Values can be set manually or automatically with defined functionality.Virtual properties (password) don’t get persisted in the database, because these are sensitive login information about the users which need to hash stored using hasing algorithm such as SHA256. React provides crypto to hash a password and store it into hashed_password. 

    // Encrypting Password using Crypto
     this.encryptedPassword = crypto.createHmac('sha256', this.salt)  // salt is uuid - unique universal identifier.
			.update(password)
			.digest('hex');


3.cookie-parser : https://www.npmjs.com/package/cookie-parser
Cookie parse maintains the request header element 'cookie' by populating it with a secret key that can be used at the time of the signin operation by the user.

