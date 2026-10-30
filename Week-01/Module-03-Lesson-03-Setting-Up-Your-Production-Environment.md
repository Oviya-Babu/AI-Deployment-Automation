```markdown
# Week-01/Module-03-Lesson-03-Setting-Up-Your-Production-Environment.md

# Lesson 3 of 80 — Setting Up Your Production Environment

![Production Environment](https://images.unsplash.com/photo-1558494949-ef010cbdcc31?w=1200)

**Module 1: Foundations of AI Deployment & Production Readiness**

---

## Table of Contents

1. [Introduction: Laying the Foundation for AI Deployment](#introduction-laying-the-foundation-for-ai-deployment)
2. [Essential Tools and Infrastructure for AI Production Environments](#essential-tools-and-infrastructure-for-ai-production-environments)
3. [Mastering Python Environments: venv and Conda Explained](#mastering-python-environments-venv-and-conda-explained)
4. [Introduction to Git: Version Control for AI Projects](#introduction-to-git-version-control-for-ai-projects)
5. [Essential Command-Line Interface (CLI) Skills for Developers](#essential-command-line-interface-cli-skills-for-developers)
6. [Quick Reference Summary](#quick-reference-summary)

---

## Introduction: Laying the Foundation for AI Deployment

![Foundation](https://images.unsplash.com/photo-1518770660439-4636190af475?w=1200)

Welcome to the foundational module of our AI Deployment, Automation & Real-World Applications course! As B-Tech students, you're on the cusp of transforming theoretical AI/ML knowledge into tangible, impactful solutions. This lesson, **'Setting Up Your Production Environment,'** is your critical first step. It bridges the gap between developing models in isolation and preparing them for the dynamic, demanding world of production.

In this session, we will demystify the essential tools and practices that form the bedrock of any successful AI deployment. We'll explore why a well-configured environment is not just a convenience, but a necessity for **reproducibility, scalability, and maintainability**. You'll gain hands-on experience with fundamental tools like **Python virtual environments** and **Git**, which are indispensable for any software development, especially in the complex domain of AI.

### Learning Objectives for This Lesson

- Understand the core components of a production-ready AI environment.
- Master the setup and utilization of Python virtual environments (venv and conda) for project isolation.
- Grasp the fundamentals of Git for version control and collaborative development.
- Become proficient in basic Command-Line Interface (CLI) operations essential for managing your environment and tools.
- Gain practical experience in setting up and interacting with a Git repository.
- Learn and apply best practices for robust environment management.

These objectives directly support the module's overarching goals:

| Module Goal | How This Lesson Contributes |
|---|---|
| Understand the AI model deployment lifecycle | Focuses on the crucial 'preparation' and 'setup' phases within this lifecycle. |
| Define key terms related to AI production | Introduces and explains terms like 'virtual environment,' 'repository,' 'commit,' 'push,' and 'CLI.' |
| Identify prerequisites for successful AI deployment | A well-managed environment is a primary prerequisite. |
| Outline the benefits of robust deployment strategies | The practices covered here contribute directly to a more robust and reliable deployment strategy. |

The real-world relevance of this lesson cannot be overstated. Imagine building a groundbreaking AI model only to find it fails when deployed because of conflicting dependencies or an inability to track changes. This is a common pitfall that robust environment setup prevents. Whether you're deploying a recommendation engine, a natural language processing service, or a computer vision model, the principles of **environment management, version control, and command-line proficiency are universal**. They ensure that your AI solutions are not only functional but also reliable, reproducible, and scalable.

Let's embark on this essential journey to build a solid foundation for your AI deployment endeavors.

---

## Essential Tools and Infrastructure for AI Production Environments

![Infrastructure](https://images.unsplash.com/photo-1451187580459-43490279c0fa?w=1200)

Before we dive into the specifics of setting up our local environment, it's crucial to understand the landscape of tools and infrastructure that support AI model deployment in a production setting. This provides context for why the practices we'll learn are so important.

### What are Essential Tools and Infrastructure?

An AI production environment is a carefully orchestrated system designed to host, serve, monitor, and manage AI models reliably and efficiently. It encompasses hardware, software, and services that enable an AI model to perform its intended function for end-users or other systems. The 'essential' components can be broadly categorized:

| Category | Description |
|---|---|
| **Compute Resources** | The processing power needed to run your AI models. Ranges from powerful CPUs to specialized GPUs (Graphics Processing Units) or TPUs (Tensor Processing Units) for deep learning tasks. In production, this often translates to cloud-based virtual machines, container orchestration platforms, or managed AI services. |
| **Storage** | Where your data, models, code, and logs are stored. Includes databases for structured data, object storage for large files (like model artifacts or datasets), and file systems. |
| **Networking** | How your AI services communicate with users and other systems. Involves load balancers, API gateways, firewalls, and content delivery networks (CDNs). |
| **Orchestration and Management** | Tools that automate the deployment, scaling, and management of your AI applications. Kubernetes is a prime example, allowing you to manage containerized applications at scale. |
| **Monitoring and Logging** | Systems to track the performance, health, and behavior of your AI models and the surrounding infrastructure. Includes metrics collection (e.g., latency, error rates, resource utilization), log aggregation, and alerting. |
| **CI/CD Pipelines** | Continuous Integration and Continuous Deployment pipelines automate the process of building, testing, and deploying new versions of your AI models and applications. |
| **Development Tools** | The software developers use to build and manage their projects (focus of this lesson): Programming languages (Python), package managers (pip, conda), version control systems (Git), containerization (Docker), Infrastructure as Code (Terraform, CloudFormation). |

### Why are these Tools and Infrastructure Important?

The complexity of AI models and the demands of production environments necessitate a robust setup. Here's why these components are critical:

- **Reproducibility:** Production environments must be able to reproduce the exact conditions under which a model was trained and tested. This is vital for debugging, auditing, and ensuring consistent performance. Tools like Docker and virtual environments are key here.
- **Scalability:** As user demand grows, your AI service must scale accordingly. Orchestration platforms like Kubernetes, coupled with scalable compute resources, enable this.
- **Reliability and Availability:** Production systems need to be highly available and fault-tolerant. Redundancy, automated failover, and robust monitoring are essential.
- **Maintainability:** Over time, models need to be updated, retrained, and improved. Version control (Git) and CI/CD pipelines streamline this process.
- **Cost-Effectiveness:** Efficient resource utilization, auto-scaling, and optimized infrastructure management contribute to controlling operational costs.
- **Security:** Protecting sensitive data, model intellectual property, and the infrastructure itself is paramount. This involves secure coding practices, access control, and network security.

### Real-World Scenarios

- **E-commerce Recommendation Engine:** A company deploys a recommendation engine. Initially, it runs on a single server. As sales increase, the engine needs to handle millions of requests per day. This requires scaling compute resources, load balancing, and efficient model serving. Version control ensures that updates to the recommendation algorithm can be rolled out safely.
- **Medical Image Analysis:** A hospital uses an AI model to detect anomalies in X-rays. The model must be highly accurate and its performance must be consistently monitored. Any drift in performance due to changes in imaging equipment or patient demographics needs to be detected and addressed quickly. Logging and monitoring tools are critical for this.
- **Autonomous Driving Systems:** These systems rely on complex AI models for perception, decision-making, and control. The development and deployment process involves massive datasets, extensive simulation, rigorous testing, and continuous updates. Git is used by thousands of engineers to manage the codebase, and Kubernetes orchestrates the deployment of various AI components.

In essence, the tools and infrastructure form the ecosystem that allows your AI models to move from a research notebook to a valuable, operational asset. Our focus in this lesson on **Python environments and Git** directly contributes to the development toolchain, ensuring that your local development and collaboration efforts are aligned with production best practices.

---

## Mastering Python Environments: venv and Conda Explained

![Python Environments](https://images.unsplash.com/photo-1526379095098-d400fd0bf935?w=1200)

In the world of software development, and particularly in AI/ML, managing dependencies is paramount. Different projects often require different versions of libraries, and conflicts can arise if everything is installed globally. This is where **virtual environments** come into play. They provide isolated Python environments for each project, ensuring that dependencies for one project do not interfere with another.

### What are Python Virtual Environments?

A virtual environment is a self-contained directory tree that includes a specific Python installation and any number of additional packages. When you activate a virtual environment, your system's Python interpreter and installed packages are temporarily replaced by those within the environment. This isolation is crucial for:

- **Dependency Management:** Each project can have its own set of dependencies, including specific versions of libraries like NumPy, Pandas, TensorFlow, or PyTorch.
- **Reproducibility:** You can easily recreate the exact environment for a project on another machine or for another developer by listing the installed packages and their versions.
- **Avoiding Conflicts:** Prevents situations where Project A needs library X version 1.0, while Project B needs library X version 2.0.
- **Cleanliness:** Keeps your global Python installation tidy and free from project-specific clutter.

We will cover two primary methods for creating and managing virtual environments: **venv** (built into Python 3.3+) and **conda** (part of the Anaconda/Miniconda distribution).

### 1. Using venv

`venv` is the standard, lightweight way to create virtual environments in Python 3. It's included with Python itself, so you do not need to install anything extra if you have a recent Python version.

**Why use venv?**

- **Built-in:** No external installation required for Python 3.3+.
- **Lightweight:** Creates minimal overhead.
- **Standard:** Widely adopted and understood.

#### How to Implement venv

Let's assume you have Python 3 installed. Navigate to your project directory in your terminal.

**Step 1: Create a Virtual Environment**

Use the `venv` module to create a new environment. A common convention is to name the environment directory `.venv` or `venv`.

```bash
python -m venv .venv
```

This command creates a directory named `.venv` (or whatever you choose) containing a copy of the Python interpreter and necessary files.

**Step 2: Activate the Virtual Environment**

Activation is operating system dependent:

On **Windows** (Command Prompt/PowerShell):

```bash
.venv\Scripts\activate
```

On **macOS/Linux** (Bash/Zsh):

```bash
source .venv/bin/activate
```

Once activated, your terminal prompt will usually change to indicate the active environment (e.g., `(.venv) user@machine:~/project$`).

**Step 3: Install Packages**

With the environment active, you can install packages using `pip`. These packages will only be installed within this virtual environment.

```bash
pip install numpy pandas fastapi uvicorn
```

**Step 4: Deactivate the Virtual Environment**

When you're done working in the environment, you can deactivate it:

```bash
deactivate
```

Your prompt will return to normal.

**Step 5: Generating a Requirements File**

To share your project's dependencies, create a `requirements.txt` file:

```bash
pip freeze > requirements.txt
```

This file lists all installed packages and their exact versions. Another user can then create their own virtual environment, activate it, and install all dependencies with:

```bash
pip install -r requirements.txt
```

**Real-World Scenario:**

You are working on a web application using FastAPI. Project A requires FastAPI version 0.100.0, while Project B, a newer project, requires FastAPI version 0.115.0. Using venv, you can create separate environments for each project, install the respective FastAPI versions in each, and avoid any conflicts. When you need to work on Project A, you activate its environment; for Project B, you activate its environment.

### 2. Using conda

`conda` is a powerful package, dependency, and environment management system. It's particularly popular in the data science and machine learning communities because it can manage packages written in Python, R, and other languages, and it handles complex binary dependencies more effectively than pip alone.

**Why use conda?**

- **Cross-Language Support:** Manages packages for Python, R, C++, etc.
- **Complex Dependencies:** Excellent at resolving intricate binary dependencies, especially for scientific libraries (e.g., NumPy, SciPy, TensorFlow with GPU support).
- **Environment Creation:** Can create environments with specific Python versions (e.g., Python 3.8, 3.9, 3.10) easily.
- **Anaconda/Miniconda:** Comes bundled with Anaconda (a large distribution with many pre-installed packages) or Miniconda (a minimal installer).

#### How to Implement conda

First, ensure you have Anaconda or Miniconda installed. You'll interact with conda via your terminal.

**Step 1: Create a Conda Environment**

You can create an environment and specify the Python version and initial packages:

```bash
conda create --name myenv python=3.10 pandas numpy fastapi uvicorn
```

Replace `myenv` with your desired environment name. This command creates a new environment named `myenv` with Python 3.10 and installs the specified packages.

**Step 2: Activate the Conda Environment**

Activation is straightforward:

```bash
conda activate myenv
```

Similar to venv, your prompt will change to indicate the active environment (e.g., `(myenv) user@machine:~/project$`).

**Step 3: Install Additional Packages**

You can install more packages using `conda install` or `pip install` (conda can use pip packages too):

```bash
conda install scikit-learn
pip install langchain==0.2.0
```

**Step 4: Deactivate the Conda Environment**

To exit the environment:

```bash
conda deactivate
```

**Step 5: Exporting and Recreating Conda Environments**

To share your environment, you can export its specifications:

```bash
conda env export > environment.yaml
```

The `environment.yaml` file contains the environment name, channels (package sources), dependencies (including Python version and specific packages), and pip-installed packages. To recreate the environment on another machine:

```bash
conda env create -f environment.yaml
```

### Choosing Between venv and conda

| Use Case | Recommended Tool |
|---|---|
| Most Python projects, web development, simpler scripts where you primarily need Python packages | **venv** (lighter, built-in) |
| Managing environments with different Python versions, non-Python dependencies, complex scientific/ML libraries with intricate binary requirements | **conda** |

For this course, understanding both is beneficial. We'll primarily use **venv** for its simplicity and ubiquity in standard Python development, but be aware of conda's power for more specialized ML workflows.

---

## Introduction to Git: Version Control for AI Projects

![Git](https://images.unsplash.com/photo-1556075798-4825dfaaf498?w=1200)

In the fast-paced world of AI development, where codebases evolve rapidly and collaboration is key, managing changes effectively is not just a best practice – it's a necessity. This is where **Git**, the distributed version control system, becomes indispensable. Git allows you to track every modification made to your project's files, revert to previous states, collaborate seamlessly with others, and maintain a clear history of your work.

### What is Git?

Git is a free and open-source **distributed version control system** designed to handle everything from small to very large projects with speed and efficiency. It's built around the concept of tracking changes to files over time. Unlike centralized systems where a single server holds the entire history, Git is distributed. This means every developer has a full copy of the project's history on their local machine, enabling offline work and providing a robust backup.

### Key Concepts in Git

| Concept | Description |
|---|---|
| **Repository (Repo)** | A collection of files and their complete history. It's essentially your project's folder managed by Git. |
| **Commit** | A snapshot of your project at a specific point in time. Each commit represents a set of changes you've made and saved. Commits are uniquely identified by a SHA-1 hash. |
| **Branch** | An independent line of development. Branches allow you to work on new features or bug fixes without affecting the main codebase (often called the main or master branch). |
| **Merge** | The process of combining changes from one branch into another. |
| **Clone** | Creating a local copy of a remote repository. |
| **Push** | Uploading your local commits to a remote repository. |
| **Pull** | Downloading changes from a remote repository and merging them into your local branch. |
| **Staging Area (Index)** | An intermediate area where you prepare changes before committing them. |

### Why is Git Crucial for AI Deployment?

The benefits of using Git extend directly to the AI deployment lifecycle and production readiness:

- **Tracking Experimentation:** AI development often involves numerous experiments with different parameters, architectures, and datasets. Git allows you to version your code, configurations, and even scripts used for training, making it easy to reproduce specific experimental setups.
- **Collaboration:** AI projects are rarely solo efforts. Git facilitates teamwork by allowing multiple developers to work on different parts of the project simultaneously and merge their contributions without overwriting each other's work.
- **Reproducibility of Models:** While Git primarily tracks code, it's essential for reproducing the environment and logic that produced a specific model. By versioning your training scripts and configuration files, you can pinpoint the exact code that generated a particular model artifact.
- **Rollbacks and Bug Fixing:** If a new deployment introduces bugs or performance degradation, Git allows you to quickly revert to a previous, stable version of the code.
- **Auditing and History:** Git provides a complete audit trail of who made what changes, when, and why (via commit messages). This is invaluable for debugging, understanding the evolution of the project, and compliance.
- **Integration with CI/CD:** Git is the backbone of most Continuous Integration and Continuous Deployment (CI/CD) pipelines. Changes pushed to a Git repository can automatically trigger builds, tests, and deployments.
- **Managing Model Artifacts (with caution):** While Git is primarily for code, tools like Git LFS (Large File Storage) can help manage larger files like model weights, though dedicated artifact repositories are often preferred for production.

### Real-World Examples

- **Developing a new NLP model:** A team is building a sentiment analysis model. One developer works on data preprocessing, another on model architecture, and a third on evaluation metrics, all on separate branches. They then merge their work into the main branch for integration testing.
- **Deploying an updated recommendation system:** A company has a live recommendation system. They develop an improved algorithm in a new branch. After thorough testing, they merge it into the main branch and deploy it. If issues arise, they can instantly roll back to the previous version using Git.
- **Reproducing research results:** A researcher needs to reproduce the results from a paper published a year ago. By checking out the specific Git commit mentioned in the paper's appendix, they can retrieve the exact code and configuration used, along with the associated training scripts.

Understanding Git is a fundamental skill for any developer, and its application in AI deployment is profound. It ensures that your development process is organized, collaborative, and robust, directly contributing to the reliability of your deployed AI solutions.

---

## Essential Command-Line Interface (CLI) Skills for Developers

![CLI](https://images.unsplash.com/photo-1629654297299-c8506221ca97?w=1200)

The **Command-Line Interface (CLI)**, often referred to as the terminal or shell, is a powerful tool that allows you to interact with your computer by typing commands. While graphical user interfaces (GUIs) are intuitive for many tasks, the CLI offers unparalleled efficiency, automation capabilities, and direct control, especially for developers working with tools like Git, Docker, Python environments, and cloud platforms.

### What is the Command-Line Interface (CLI)?

The CLI is a text-based interface where users input commands, and the system responds by executing them. Common shells include **Bash** (on Linux/macOS), **Zsh** (on macOS), and **PowerShell or Command Prompt** (on Windows). For AI development, mastering a few core CLI commands is essential for managing your projects, environments, and deployments.

### Why are CLI Skills Essential for AI Deployment?

The tools and platforms used in AI deployment heavily rely on CLI interactions:

- **Tool Management:** Installing, updating, and running tools like Git, Docker, Python package managers (pip, conda), and cloud SDKs (AWS CLI, gcloud CLI, Azure CLI) are primarily done via the CLI.
- **Environment Control:** Activating virtual environments (venv, conda), managing Docker containers, and interacting with Kubernetes clusters are all CLI-driven.
- **Automation:** Scripts written in Bash or Python often orchestrate complex deployment workflows, and these scripts are executed from the command line.
- **Remote Access:** Connecting to remote servers (e.g., cloud instances) for deployment or debugging is typically done via SSH (Secure Shell), a CLI tool.
- **Efficiency:** For repetitive tasks, typing a single command is far faster than navigating through multiple GUI menus.
- **Reproducibility:** CLI commands can be scripted, ensuring that setup and deployment processes are repeatable and consistent.

### Core CLI Commands and Concepts

Let's cover some fundamental commands that you'll use frequently. We'll use Bash/Zsh syntax, which is common on Linux and macOS. Windows users can use PowerShell or Command Prompt, with some command variations.

#### 1. Navigation Commands

| Command | Description |
|---|---|
| `pwd` | **Print Working Directory:** Shows your current location in the file system. |
| `ls` | **List:** Lists the files and directories in the current directory. |
| `ls -l` | Long listing format (permissions, owner, size, date). |
| `ls -a` | Show all files, including hidden ones (those starting with a dot '.'). |
| `cd` | **Change Directory:** Moves you to a different directory. |
| `cd ..` | Move up one directory level. |
| `cd ~` | Go to your home directory. |
| `cd /path/to/directory` | Go to a specific directory. |
| `cd -` | Go to the previous directory you were in. |

#### 2. File and Directory Management

| Command | Description |
|---|---|
| `mkdir` | **Make Directory:** Creates a new directory. |
| `mkdir my_new_folder` | Create a folder named `my_new_folder`. |
| `touch` | Creates an empty file or updates the timestamp of an existing file. |
| `touch my_new_file.txt` | Create an empty file. |
| `cp` | **Copy:** Copies files or directories. |
| `cp source_file.txt destination_file.txt` | Copy a file. |
| `cp -r source_directory destination_directory` | Recursive copy of directories (`-r`). |
| `mv` | **Move:** Moves or renames files and directories. |
| `mv old_name.txt new_name.txt` | Rename a file. |
| `mv file.txt /path/to/new/location/` | Move a file. |
| `rm` | **Remove:** Deletes files or directories. Use with extreme caution! |
| `rm file_to_delete.txt` | Delete a file. |
| `rm -r directory_to_delete` | Recursive deletion of directories (`-r`). |
| `rm -rf directory_to_delete` | Recursive + force (`-f`) – very dangerous! |

#### 3. Text File Manipulation

| Command | Description |
|---|---|
| `cat` | **Concatenate:** Displays the content of a file. |
| `cat my_file.txt` | Display file contents. |
| `less` | Displays file content one screen at a time, allowing scrolling. More useful for large files than `cat`. Press `q` to exit. |
| `head` | Displays the first few lines of a file (default 10). |
| `head -n 20 my_file.txt` | Show first 20 lines. |
| `tail` | Displays the last few lines of a file (default 10). Useful for logs. |
| `tail -n 50 my_log_file.log` | Show last 50 lines. |
| `tail -f my_log_file.log` | Follow the file, showing new lines as they are added – great for monitoring logs in real-time. |

#### 4. Permissions and Ownership (Linux/macOS)

| Command | Description |
|---|---|
| `chmod` | Changes file permissions. |
| `chown` | Changes file ownership. |

#### 5. Package Management (Examples)

```bash
pip install package_name
conda create --name env_name
```

#### 6. Git Commands (covered in detail next)

```bash
git init
git clone url
git add .
git commit -m "message"
git push
git pull
```

#### 7. Running Scripts

```bash
python your_script.py
./your_executable_script    # if the script has execute permissions
```

### Tips for Effective CLI Usage

- **Tab Completion:** Press the `Tab` key to auto-complete commands, file names, and directory names. This saves typing and reduces errors.
- **Command History:** Use the Up and Down arrow keys to cycle through previously entered commands.
- **Aliases:** Create shortcuts for frequently used commands (e.g., `alias ll='ls -lha'`).
- **Man Pages:** For any command, type `man command_name` (e.g., `man ls`) to view its manual page, which details all its options and usage.
- **Redirection:** Use `>` to redirect output to a file (overwriting) and `>>` to append output to a file.
- **Piping:** Use `|` to chain commands, sending the output of one command as the input to another (e.g., `ls -l | grep .py` to list only Python files).

### Real-World Scenario

You've just downloaded a new AI project. You need to:

1. Navigate to the project directory: `cd ~/projects/new_ai_project`
2. Create a Python virtual environment: `python -m venv .venv`
3. Activate it: `source .venv/bin/activate`
4. Install dependencies from a requirements file: `pip install -r requirements.txt`
5. Run the training script: `python train.py --epochs 10 --learning_rate 0.001`

All these steps are performed efficiently using basic CLI commands. Without CLI proficiency, managing these fundamental development tasks would be significantly more cumbersome and error-prone.

---

## Quick Reference Summary

### Tool Comparison at a Glance

| Tool | Purpose | When to Use |
|---|---|---|
| **venv** | Python virtual environment (built-in) | Standard Python projects, web dev, simpler scripts |
| **conda** | Cross-language environment & package manager | Scientific/ML libraries, complex binary dependencies, multiple Python versions |
| **Git** | Distributed version control | Tracking code changes, collaboration, rollbacks, CI/CD integration |
| **CLI (Bash/Zsh)** | Text-based system interaction | Tool management, automation, remote access, environment control |

### venv Workflow (Quick Reference)

```bash
python -m venv .venv          # Create environment
source .venv/bin/activate     # Activate (macOS/Linux)
# .venv\Scripts\activate      # Activate (Windows)
pip install -r requirements.txt   # Install dependencies
pip freeze > requirements.txt     # Export dependencies
deactivate                    # Exit environment
```

### conda Workflow (Quick Reference)

```bash
conda create --name myenv python=3.10   # Create environment
conda activate myenv                     # Activate
conda install scikit-learn               # Install packages
conda env export > environment.yaml      # Export environment
conda env create -f environment.yaml     # Recreate environment
conda deactivate                         # Exit environment
```

### Essential Git Commands

```bash
git init                    # Initialize a new repository
git clone <url>             # Clone a remote repository
git add .                   # Stage all changes
git commit -m "message"     # Commit staged changes
git push                    # Push commits to remote
git pull                    # Pull changes from remote
git branch                  # List branches
git checkout -b new-branch  # Create and switch to a new branch
git merge branch-name       # Merge a branch into the current one
```

### Essential CLI Commands

```bash
pwd                         # Show current directory
ls -la                      # List all files with details
cd <path>                   # Change directory
mkdir <name>                # Create directory
touch <file>                # Create empty file
cp <src> <dest>             # Copy file/directory
mv <src> <dest>             # Move/rename
rm <file>                   # Delete file (use -r for directories)
cat <file>                  # Display file contents
head -n 20 <file>           # Show first 20 lines
tail -f <logfile>           # Follow log file in real-time
```

*End of Lesson 3 of 80*
```