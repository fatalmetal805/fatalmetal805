- 👋 Hi, I’m @fatalmetal805
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
fatalmetal805/fatalmetal805 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
steps:
- uses: actions/checkout@v2
- uses: actions/setup-java@v2
  with:
    distribution: 'temurin' # See 'Supported distributions' for available options
    java-version: '17'
- run: java -cp java HelloWorldApp./*
- name: Deploy to App Engine
  uses: google-github-actions/deploy-appengine@v0.2.0
  with:
    deliverables: app.yaml
    project_id: ${{ secrets.GCP_PROJECT }}
    credentials: ${{ secrets.GCP_SA_KEY }}
    promote: false
    version: v0
Slmgr/*/
