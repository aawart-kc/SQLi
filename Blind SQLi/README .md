## 🔍 What is Blind SQL Injection?

**Blind SQL injection** occurs when an application is vulnerable to SQL injection, but the HTTP responses do **not** display the results of the injected SQL queries or any database error messages.

In blind SQL injection, you **can’t directly see the output** of your queries in the webpage. This means techniques like `UNION-based SQLi` (which require visible results) won't work. Instead, you rely on **indirect clues** like:

- `True/False` logic
- `Time delays`
- `Error messages`

These help you infer the data **bit by bit**, making the process slower but still effective in extracting sensitive information.

---

### 🧩 Types of Blind SQL Injection

1. **Conditional Responses**  
   You craft payloads that change the application's behavior based on **true/false** conditions. Example: check if the first character of the admin password is `'a'`.

2. **Conditional Errors**  
   Even when the application doesn't return different pages, it might trigger an **error** when a condition is true/false.

3. **Time-Based Blind SQL Injection**  
   When there are **no visible errors or response changes**, you use SQL functions like `SLEEP()` or `WAITFOR DELAY` to **measure time-based responses**.

4. **Verbose SQL Error Messages**  
   Some poorly secured apps reveal **raw SQL errors**, which you can manipulate to infer backend structure and data.

---

Blind SQLi may be slower than regular SQLi, but it's still **powerful and dangerous** if not properly mitigated.
