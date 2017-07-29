# RSI

## Connecting to RSI
(almost) Everything regarding spectrum requires being connected to an RSI account, as the api doesn't support "bot account" such as there are on discord.

As such, to access spectrum you're gonna need the credentials of an account you own.

<aside class="warning">
Please remember that under the T.O.S, you are allowed multiple accounts, however only <strong>one</strong> of those can be used to post to spectrum. 
</aside>


### Sign-in
End point to sign-in via username/password

```json
{
    success: boolean;
    code: 'ErrMultiStepRequired' | 'ErrCaptchaRequired' | 'ErrWrongPassword_username'
    msg: any;
}
```

POST: ```api/account/signin```

Paramaters | Type | Description
------ | ------ | ------
username | `string` | the username to try and login with
password | `string` | the password (in clear)


### Multi-auth confirm
End point to confirm sign-in with a MFA code.

POST: ```api/account/signinMultiStep```

Paramaters | Type  | Description
------ | ------ | -----
code | `string` | the multi-factor auth code.
device_name | `string` | name to save the current device under
device_type | `'computer'` | type of the current device
duration | `'session'` | duration to trust the device