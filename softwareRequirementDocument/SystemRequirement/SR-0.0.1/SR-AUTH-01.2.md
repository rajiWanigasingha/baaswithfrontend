| ID     | SR-AUTH-01.1         |
|--------|----------------------|
| Author | Rajinda Wanigasingha |
| Date   | 2025/01/09           |

## Login to the system

**Description**

- System shall login/give access to any user with valid email address and a password if both exist in the adminUser table.

**Inputs**

- Email : Must be complied with [SR_SECURITY-01.1](./SR-SECURITY-01.1.md)
- Password : Must be complied with [SR_SECURITY-01.2](./SR-SECURITY-01.2.md)

**Output**

- JWT token
- User details : user-name, user-id ,user-role
- Unauthorized error : If email or password incorrect of doesn't exist
- Validate error : If validation fails.
- User doesn't exist : If user can't be found

**Action**

1. System shall validate user inputs according to [SR_SECURITY-01.1](./SR-SECURITY-01.1.md) and [SR_SECURITY-01.2](./SR-SECURITY-01.2.md).
    - If validation failed, System shall output `Validate Error`
2. System shall check if provided email exist in adminUser table, if not system shall output `User doesn't exist` error
3. If email exist, system shall check if password match between input password and stored password. 
4. System shall decrypted stored password to validate input password, but not in any way edit the password
5. If validation is successful system shall output JWT token and User-details

**Requirements**

- Email and a password

**Side effects**

None

**Pre-conditions and post-conditions**

None
