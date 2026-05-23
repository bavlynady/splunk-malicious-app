# Splunk Malicious App

## ⚠️ Warning

This project should be used for **ethical purposes only**.

Use it only in a legal lab environment, CTF, or authorized penetration testing engagement.

Do not use this app on any system you do not own or do not have permission to test.

---

## Structure

```text
Splunk Runtime/
├── bin/
│   └── runtime.py
├── default/
│   ├── app.conf
│   └── commands.conf
└── metadata/
    └── default.meta
```

- `bin/runtime.py`  
  The main Python file that runs the command.

- `default/commands.conf`  
  Registers the Splunk command.

- `default/app.conf`  
  Contains the app configuration.

- `metadata/default.meta`  
  Contains app permissions.

---

## How to Run

### 1. Install the App

Install the app in Splunk.

---

### 2. Write the Command in Base64

Write the command you want to run in Base64.

Example command:

```bash
whoami
```

Base64 payload:

```text
d2hvYW1p
```

Run it in Splunk:

```spl
* | script runtime d2hvYW1p
```

---

### 3. Add New Local File & Directory

Go to:

```text
Settings > Data Inputs > New Local File & Directory
```

Note:

If you encounter this error:

```text
Unable to locate the configuration file for this url
```

it’s temporary — simply retrying the step should resolve it.

---

### 4. Add the Output File

Write this in the **File or Directory** bar:

```text
/tmp/output.txt
```

Then click **Next**.

---

### 5. View the Output

You should see the command you ran previously.
