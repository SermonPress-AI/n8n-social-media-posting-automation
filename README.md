# n8n Social Media Posting Automation

Part of the **SermonPressAI** open-source workflow collection, this repository contains **n8n workflows for churches that automatically generate and post sermon announcements to social media**.

When a church uploads its latest sermon, these workflows pull the sermon’s title, passage, description, and link, then format them into multiple ready-to-use post options for platforms like Facebook. Each post is biblically grounded, engaging, and written to encourage viewers to watch the full sermon.

---

## 📌 Features

* **Automatic Post Generation** – Creates multiple post variations when a new sermon is uploaded.
* **Biblically Rooted Content** – Pulls from the sermon’s text and theme to produce Christ-centered summaries.
* **Custom Formatting** – Includes clickable links to the full sermon and can embed Scripture references.
* **Multi-Platform Ready** – Posts can be sent to Facebook automatically, with options to add Instagram, Twitter/X, and more.
* **Workflow Modularity** – Churches can adapt templates, tone, and formatting to fit their congregation’s style.
* **No Manual Copy/Paste** – Automates repetitive posting tasks while maintaining quality and theological accuracy.

---

## 🛠 Requirements

* **n8n** (self-hosted or cloud)
* Access to your church’s sermon data (API, RSS feed, Wordpress, or other integration)
* API credentials for connected social media platforms
  *(Store securely in n8n’s credentials manager or a `.env` file — never commit credentials to the repository.)*

### Environment Variables & Credentials

| Name | Purpose | Where to set |
| ---- | ------- | ------------ |
| `WORDPRESS_BASE_URL` | Base URL of your WordPress site (without trailing slash). Used by HTTP Request nodes to pull sermon data. | Environment variable in n8n |
| `OpenAi account` | OpenAI API key used for generating Facebook post content. | n8n credentials manager |

---

## 📂 Repository Structure

```
.gitignore                       - Prevents committing sensitive or local files
LICENSE                          - MIT Open-Source Licensing
README.md                        - This file
wordpress-to-facebook-posting.json - Example n8n workflow
```

---

## 🚀 Setup & Usage

1. **Clone the Repository**
   Start by downloading the JSON file onto your computer and then uploading that file to the n8n new project. You will then see a workflow already built, but you need to plug in the data for the individual nodes. Go to this link to download the workflow
   ```bash
   git clone https://github.com/SermonPress-AI/n8n-social-media-posting-automation.git
   cd n8n-social-media-posting-automation
   ```

2. **Import Workflows into n8n**

   * Open n8n.
   * Go to **Import from File** and select the `wordpress-to-facebook-posting.json` workflow file.

3. **Getting the workflow running**
    *Pull data from WordPress Sermon Post & Pull transcript from wordpress data: 
	edit the node and plug in the website url (including the "https://") into the node. Set the "Method" to "GET" then run the node to see if it runs
	* Generate Facebook post content: 
 	with the node, you will take the OpenAI key and either use the default prompt given or plug in your own prompt to use 


  * Human-in-the-loop
	Add your own credential by signing into your google account and then change the "to" section to your own email. after you run the node and all of the nodes before it you should get an email where you can approve or deny the information given



4. **Configure Credentials**
   

   * Add Facebook and any other platform credentials to n8n’s credentials manager.
   * Connect your sermon data source (API, RSS feed, etc.).

6. **Test the Workflow**

   * Trigger the workflow manually with sample sermon data.
   * Verify the generated posts and ensure they appear correctly on your social media accounts.

---

## 🔒 Security Notes

* Never commit API keys, tokens, or passwords.
* Use n8n’s built-in credentials manager for sensitive information.

### Environment-specific exclusions

The repository's `.gitignore` prevents committing local files that should remain private, including:

* `.env` – environment variables
* `credentials.json` – service credentials
* `node_modules/` – installed dependencies

Add any other files specific to your setup to `.gitignore` to keep them out of version control.

---

## 📜 License

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

---

## 🌐 About SermonPressAI

**SermonPressAI** is an open-source initiative providing modular automation workflows for churches.
Each repository serves a specific function — from transcription, to content generation, to social posting — allowing churches to pick and choose the tools that fit their needs.

---

## 🤝 Contributing

We welcome contributions from developers, churches, and volunteers:

* Fork this repository
* Create a new branch for your feature or fix
* Submit a pull request with a clear description

---

## 📧 Contact

For questions or support, reach out via the SermonPressAI GitHub Discussions or Issues page.
