<a id="reset-password-confirm" href="#"></a>
###reset_password_confirm($login_column_value, $code, $decode = true)

----------

The reset_password_confirm method returns a boolean if the reset password has been confirmed or not. If it is confirmed, the passwords are updated in the database appropriately.

Parameters                   | Type            | Default       | Description
:--------------------------- | :-------------: | :------------ | :--------------
`$login_column_value`        | string          |               | The users login ( email or username ).
`$code`                      | string          |               | The password reset hash.
`$decode`                    | bool            | true          | If the login value needs to be decoded.

`returns` bool, array `throws` SentryException

> **Notes:** If the user logs in to their account before confirming the reset, the reset process will be nullified.

####Example

	try
	{
	    // confirm password reset
	    $confirm_reset = Sentry::reset_password_confirm('VGhpcyBpcyBhbiBlbmNvZGVkIHN0cmluZw==', '93kavFY63S8jtala93a76fQ...');
	    // or
	    $confirm_reset = Sentry::reset_password_confirm('john.doe@domain.com', '93kavFY63S8jtala93a76fQ...', true);

	    if ($confirm_reset)
	    {
	        // show success page or redirect to login - or whatever you want
	    }
	    else
	    {
	        // password was not reset - bad login/hash combo
	    }

	}
	catch (SentryAuthException $e)
	{
	    // issue activating the user
	    // store/set and display caught exceptions such as a user not existing or user is disabled
	    $errors = $e->getMessage();
	}
