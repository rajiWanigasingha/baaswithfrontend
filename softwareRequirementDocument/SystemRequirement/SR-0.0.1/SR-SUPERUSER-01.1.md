| ID     | SR-SUPERUSER-01.1    |
|--------|----------------------|
| Author | Rajinda Wanigasingha |
| Date   | 2025/01/09           |

## Super-user shall be able to create new users

**Description**

- System shall give super-user, permission to create new users with different roles.

**Inputs**

- username : Must be a string
- Email : Must be complied with [SR_SECURITY-01.1](./SR-SECURITY-01.1.md)
- Password : Must be complied with [SR_SECURITY-01.2](./SR-SECURITY-01.2.md)

**Output**

- JWT token
- Validate error : If validation fails.

**Action**

1. System shall validate super-user inputs according to [SR_SECURITY-01.1](./SR-SECURITY-01.1.md) and [SR_SECURITY-01.2](./SR-SECURITY-01.2.md).
    - If validation failed, System shall output `Validate Error`
2. System shall create new user using valid email, password and the username with any role.

**Requirements**

- Email, password and username

**Side effects**

- None

**Pre-conditions**

- System shall verify this action only can be taken by a super-user

**post-conditions**

- None