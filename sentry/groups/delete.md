<a id="delete" href="#"></a>
###delete()

----------

The delete method deletes the current group and all associations to it.

`returns` bool `throws` SentryException

####Example

	try
	{
	    if (Sentry::group(4)->delete())
	    {
	        // group was deleted
	    }
	    else
	    {
	        // group was not deleted
	    }
	}
	catch (SentryGroupException $e)
	{
	    $errors = $e->getMessage();
	}
