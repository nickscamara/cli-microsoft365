# aad user set

Updates information of the specified user

## Usage

```sh
m365 aad user set [options]
```

## Options

`-i, --objectId [objectId]`
: The object ID of the user to update. Specify `objectId` or `userPrincipalName` but not both.

`-n, --userPrincipalName [userPrincipalName]`
: User principal name of the user to update. Specify `objectId` or `userPrincipalName` but not both.

`--accountEnabled [accountEnabled]`
: Boolean value specifying whether the account is enabled. Valid values are `true` or `false`.

`--resetPassword`
: If specified, the password of the user will be reset. This will make the parameter `newPassword` required.

`--forceChangePasswordNextSignIn`
: If specified, the user will have to change his password the next time they log in. Can only be set in combination with `resetPassword`.

`--currentPassword [currentPassword]`
: Current password of the user that is signed in. If this parameter is set, `newPassword` is mandatory. Can't be combined with `resetPassword`.

`--newPassword [newPassword]`
: New password to be set. Must be set when specifying either `resetPassword` or `currentPassword`.

--8<-- "docs/cmd/_global.md"

## Remarks

You can update information of a user, either by specifying that user's id (`objectId`) or user name (`userPrincipalName`), but not both.

If the user with the specified id or user name doesn't exist, you will get a `Resource 'xyz' does not exist or one of its queried reference-property objects are not present.` error.

## Examples

Update specific property _department_ of user with id _1caf7dcd-7e83-4c3a-94f7-932a1299c844_

```sh
m365 aad user set --objectId 1caf7dcd-7e83-4c3a-94f7-932a1299c844 --Department IT
```

Update multiple properties of user with name _steve@contoso.onmicrosoft.com_

```sh
m365 aad user set --userPrincipalName steve@contoso.onmicrosoft.com --Department "Sales & Marketing" --CompanyName Contoso
```

Enable user with id _1caf7dcd-7e83-4c3a-94f7-932a1299c844_

```sh
m365 aad user set --objectId 1caf7dcd-7e83-4c3a-94f7-932a1299c844 --accountEnabled true
```

Disable user with id _1caf7dcd-7e83-4c3a-94f7-932a1299c844_

```sh
m365 aad user set --objectId 1caf7dcd-7e83-4c3a-94f7-932a1299c844 --accountEnabled false
```

Enable user with id _1caf7dcd-7e83-4c3a-94f7-932a1299c844_

```sh
m365 aad user set --objectId 1caf7dcd-7e83-4c3a-94f7-932a1299c844 --accountEnabled true
```

Reset password of a given user by userPrincipalName and require the user to change the password on the next sign in

```sh
m365 aad user set --userPrincipalName steve@contoso.onmicrosoft.com --resetPassword --newPassword 6NLUId79Lc24 --forceChangePasswordNextSignIn
```

Change password of the currently logged in user

```sh
m365 aad user set --objectId 1caf7dcd-7e83-4c3a-94f7-932a1299c844 --currentPassword SLBF5gnRtyYc --newPassword 6NLUId79Lc24
```

## Response

The command won't return a response on success.
