{

  "name": "Oops Link Tracker",

  "type": "TAG",

  "version": 1,

  "author": {

    "name": "Oops Tracker",

    "url": "https://oops.com"

  },

  "permissions": [

    "access_globals",

    "inject_script"

  ],

  "code": "const handler = (event) => {\n  const hostname = new URL(event.target.href).hostname;\n  if (!hostname.includes(location.hostname)) {\n    data.gtmOnSuccess();\n  }\n};\n\ndocument.body.addEventListener('click', function(e) {\n  const target = e.target.closest('a');\n  if (target && target.href) {\n    handler({ target });\n  }\n}, true);",

  "fields": [],

  "setup": [],

  "triggers": []

}

 
# Outbound Link Tracker (GTM Custom Template)
 
This tag tracks clicks on outbound links and fires a Google Tag Manager event when a user clicks a link that navigates away from your domain.
 
## 👨‍💻 How It Works
 
- Listens for `click` events on anchor (`<a>`) tags.

- Checks if the clicked link points to a different domain.

- Fires `gtmOnSuccess()` if it's an outbound link.
 
## ⚙️ Usage
 
1. Import the `template.tpl` file into GTM via Templates > New Tag Template.

2. Add a new tag using this template.

3. Set a trigger (e.g., All Pages).

4. Publish your container.
 
## 🔐 Permissions Used
 
- `access_globals` – to access `location.hostname`

- `inject_script` – to inject the event listener
 
## 📸 Screenshots
 
![screenshot](screenshot.png)
 
---
 
## 👤 Author
 
- Name: Your Name

- Website: [https://your-website.com](https://your-website.com)

 
