# 🎬 SRT Caption Translator – Dockerized ML Subtitle Translation 

A beginner-friendly, fully Dockerized **machine learning project** that translates video subtitles (`.srt` files) using the **Hugging Face Transformers** library. This project demonstrates the **complete development-to-deployment pipeline**—from local ML coding to containerization with Docker and publishing on **Docker Hub**.

> 🔗 **DockerHub Repo:** [pranayshaurya on Docker Hub](https://hub.docker.com/repositories/pranayshaurya)

---

## 🧠 Why This Project Matters

This project is **practical**, beginner-friendly, and solves a **real-world problem**: language accessibility in videos via automatic subtitle translation. It demonstrates:

- ✅ Building & customizing Docker containers
- ✅ Using Dockerfiles & Docker Compose
- ✅ Integrating Hugging Face Transformers for ML
- ✅ Mounting volumes for persistence
- ✅ Pushing images to Docker Hub for global access

Whether you're new to Docker or looking to deploy ML models in production environments, this project gives you **hands-on experience** with the full stack of tools used in modern AI/ML workflows.

---

## 💡 Key Features

- 📜 Translates `.srt` subtitle files (e.g., English → French)
- 🐳 Built on `jupyter/tensorflow-notebook` base Docker image
- 📦 Uses Hugging Face `transformers` + `pysrt`
- 📁 Volume mounting to persist input/output files
- 🔐 Custom Jupyter password authentication
- 🌐 Deployed to [Docker Hub](https://hub.docker.com/repositories/pranayshaurya)

---

## 📂 Project Structure

```
├── Dockerfile                 # Custom image setup
├── docker-compose.yml        # Container configuration
├── captions_english.srt      # Sample input subtitle file
├── translator.ipynb          # Jupyter Notebook with ML logic
└── README.md                 # This file
```

---

## 🛠️ Setup & Usage

### 🔧 Prerequisites
- Docker Desktop installed
- Basic familiarity with terminal commands

---

### 📦 Run the App Locally

```bash
# Clone this repo
git clone https://github.com/<your-username>/srt-caption-translator-docker.git
cd srt-caption-translator-docker

# Start the container
docker compose up
```

Now open your browser and navigate to:

```
http://localhost:8000
```

> Password is set inside `docker-compose.yml` (e.g., `I am Batman`)

---

### 🎯 Translate Subtitles in Jupyter Notebook

1. Open `translator.ipynb`
2. Load the `.srt` file using `pysrt`
3. Translate each subtitle using:
   ```python
   from transformers import pipeline
   translator = pipeline("translation_en_to_fr")
   ```
4. Save output as `captions_french.srt` using:
   ```python
   subs.save("captions_french.srt")
   ```

---

## 🌍 Deploy to DockerHub

Already deployed at:  
🔗 **[pranayshaurya on Docker Hub](https://hub.docker.com/repositories/pranayshaurya)**

To push your own version:

```bash
# Tag your local image
docker tag <image-id> pranayshaurya/srt-translator:1.0

# Push it
docker push pranayshaurya/srt-translator:1.0
```

To pull and run the image elsewhere:

```bash
docker pull pranayshaurya/srt-translator:1.0
docker run -p 5000:8888 pranayshaurya/srt-translator:1.0
```

---

## 📌 Example Input/Output

**Input – captions_english.srt**  
```
1
00:00:00,000 --> 00:00:02,000
My name is Maria and I am a programmer.
```

**Output – captions_french.srt**  
```
1
00:00:00,000 --> 00:00:02,000
Je m'appelle Maria et je suis programmeuse.
```

---

## 🧰 Technologies Used

- **Docker / Docker Compose**
- **Hugging Face Transformers**
- **Jupyter Notebook**
- **TensorFlow (as base image)**
- **Python 3**
- **pysrt** (Subtitle file parser)

---

## About Me

**Pranay Shaurya**  
🎓 4rd-year B.Tech CSE student at VIT Bhopal  
💼 Passionate about AI/ML, DevOps, and building practical, scalable applications  
 [Visit DockerHub Profile](https://hub.docker.com/repositories/pranayshaurya)

---

## License

This project is open source and available under the [MIT License](LICENSE).

---

## Acknowledgements

- [Hugging Face](https://huggingface.co/)
- [Jupyter Docker Stacks](https://jupyter-docker-stacks.readthedocs.io/en/latest/)
- [PySRT](https://pypi.org/project/pysrt/)
- [Docker Simply Explained with a Machine Learning Project for Beginners – by Kalle Hallden]– for the excellent step-by-step tutorial that inspired and guided me.

