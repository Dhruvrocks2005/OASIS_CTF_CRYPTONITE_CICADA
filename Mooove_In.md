# Mooove In

**Challenge URL**: `https://bugs.oasis.cryptonite.live/`


In this challenge, we are tasked with exploring a bug reporting system that seems to handle inputs in the URL path.

- URL: `https://bugs.oasis.cryptonite.live/`<br>Response: `No bug reported. Report at /report_bugs/{bug}`

- URL: `https://bugs.oasis.cryptonite.live/report_bugs/%7Bbug%7D`<br>Response: `"%7Bbug%7D" reported to admin && sent to command store for further processing.`

 ### Initial Observations
The encoded `{bug}` is a URL-encoded version of `%7Bbug%7D`, suggesting that we can submit a "bug" or input into the system by manipulating the URL after `/report_bugs/`.

My initial testing revealed the following:

- **Whatever I append to the URL after `/report_bugs/`** is reflected on the screen in double quotes in the format:  
  `"{submitted_value}" reported to admin && sent to command store for further processing`.

- **Semicolon (`;`) behavior**:  
  When a semicolon (`;`) is added after the input, the portion after the semicolon does not appear on the screen. This hinted at potential command execution.

- **Double ampersand (`&&`) behavior**:  
  If `&&` is included in the input, the portion before the `&&` is displayed, but the part after `&&` does not appear. Instead, the system responds with an error message: `Command not found`.
  This behavior strongly hinted at possible command injection.

### Exploit Process
Given the command injection hint, I proceeded as follows:

1. **Command Injection Testing**:  
   I attempted to inject a command by appending `&&ls` to the URL, like so:  
   `https://bugs.oasis.cryptonite.live/report_bugs/hello&&ls`.

2. **Result**:  
   The command successfully listed three files in the directory:
   - `file1.txt`
   - `file2.txt`
   - `flag.txt`

3. **Capturing the Flag**:  
   I then attempted to read the contents of the flag by modifying the URL to execute the `cat` command:  
   `https://bugs.oasis.cryptonite.live/report_bugs/hello&&cat flag.txt`.

4. **Flag Retrieved**:  
   The flag was successfully retrieved and displayed:  
   ```
   OASIS{M0v1ng_f0rw4rd_0n3_f1l3_4t_a_t1me}
   ```
   
- **No Screenshots**: Unfortunately, I was unable to provide screenshots for this write-up because the Oasis website was taken down.
