Ubuntu / WSL
    │
    ├── Create Project
    │       ├── App.java
    │       ├── pom.xml
    │       └── build.yml
    │
    ├── git add .
    ├── git commit
    └── git push
             │
             ▼
      GitHub Repository
             │
             ▼
      GitHub Actions Trigger
             │
             ▼
      Build JAR Workflow
             │
             ├── Checkout repo
             ├── Setup Java 17
             ├── mvn clean package
             └── Upload Artifact
             │
             ▼
      target/hello-jar-1.0.jar
             │
             ▼
      Artifacts → java-jar

************************************
hello-jar/
├── .git/                          # Git local repository metadata
│
├── .github/
│   └── workflows/
│       ├── build.yml              # GitHub Actions workflow
│       └── main.yml               # Optional workflow file
│
├── pom.xml                        # Maven build configuration
│
├── src/
│   └── main/
│       └── java/
│           └── com/
│               └── example/
│                   └── App.java   # Java source code
│
└── target/                        # Generated after mvn build
    ├── classes/
    ├── generated-sources/
    ├── maven-status/
    └── hello-jar-1.0.jar          # Output JAR
*******************************

mkdir hello-jar
cd hello-jar
mvn clean package
java -cp target/hello-jar-1.0.jar com.example.App
git add .

git commit -m "Build project"

git push origin main

***********************

Final Output 


target/hello-jar-1.0.jar

Repo
 └── Actions
      └── Build JAR
           └── Artifacts
                └── java-jar.zip
                     └── hello-jar-1.0.jar
      -------------88888888888*
