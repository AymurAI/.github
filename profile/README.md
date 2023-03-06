## About AymurAI
AymurAI is a software based on Artificial Intelligence (AI), which aims to help criminal courts in Latin America to collect and make available data on gender-based violence. We developed AymurAI explicitly to identify important information in court rulings and then built an open dataset to aid transparency in the judiciary. This program will help the construction of data and statistics on gender-based violence.
The creation of this prototype involved planning, discussion, and development, and it required intense work in four areas: artificial intelligence, API, frontend and data labelling. Nowadays, we have a working prototype that can help Spanish speaking Criminal Courts have datasets about their rulings.

![image](https://user-images.githubusercontent.com/8229279/216350984-d74ae5b5-e2d9-4d3a-b04d-0d6d6e125a8b.png)

You can find out more about our project in our website: https://www.aymurai.info, you can contact us at <aymurai@datagenero.com>, and you can take a look at our model in Huggingface: https://huggingface.co/aymurai/flair-ner-spanish-judicial

## Instalation guide
### Requirements
To install AymurAI in your computer there are some minimum requirements:
- Have Windows 10 or higher
- Have 6 GB of disk space free
- Have [Docker](https://docker.com) installed and running
- Download the .rar file from our releases: https://github.com/AymurAI/desktop-app/releases/ you should see which release is the last one

### Steps to install the app

1) Open Docker
2) Open PowerShell or windows command prompt and copypaste the following command:
<pre><code>docker run -p 8899:8899 -d registry.gitlab.com/collective.ai/datagenero-public/aymurai-api:prod
</code></pre>
3) After this, you should be able to see a process running in Docker called "aymuray-dev-clean"
![image](https://user-images.githubusercontent.com/8229279/216362224-413aaf64-efbc-49ba-888e-3e03b45389cf.png)
4) Download and extract the .rar file of the final release (you can download it [here](https://github.com/AymurAI/desktop-app/releases/))
5) Open the file <code>AymurAI.exe</code> that is inside the folder 
5) You can now use AymurAI to extract information from court rulings!

### Trying the app with synthetic (fake) criminal court rulings

You can try our app uploading [this criminal court ruling](https://drive.google.com/drive/folders/1h46h96gSg8vO2e3vEiINtq8XFLvcZZ7J?usp=sharing) that was created with fake names and information so everyone can use it to understand how our software works.
