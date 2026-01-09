| ID     | SR-AUTH-01.1         |
|--------|----------------------|
| Author | Rajinda Wanigasingha |
| Date   | 2025/01/09           |

## Create first super-user

**Description**

- System shall use a one-time function to create a single super-user with a valid email and a password

**Inputs**

- Email : Must be complied with [SR_SECURITY-01.1](./SR-SECURITY-01.1.md)
- Password : Must be complied with [SR_SECURITY-01.2](./SR-SECURITY-01.2.md)

**Output**

- JWT token
- User details : user-name, user-id ,user-role
- Unauthorized error : If email or password incorrect of doesn't exist
- Forbidden access error : If super-user already exist
- Validate error : If validation fails.

**Action**

1. System shall validate user inputs according to [SR_SECURITY-01.1](./SR-SECURITY-01.1.md) and [SR_SECURITY-01.2](./SR-SECURITY-01.2.md).
   - If validation failed, System shall output `Validate Error`
2. System shall check if super-user exist from an environment variable called `SUPER_USER`, if `SUPER_USER` doesn't
exist system shall output `Forbidden access error`, `SUPER_USER` environment variable shall be stored in the platform (Linux) system will run pone.
3. System shall create new super-user in adminUser table, then create `SUPER_USER` environment variable.

**Requirements**

- Email and a password
- Password must be stored hashed

**Side effects**

None

**Pre-conditions and post-conditions**

None
