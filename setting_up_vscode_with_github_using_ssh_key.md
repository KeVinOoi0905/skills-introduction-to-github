# Setting Up VS Code with GitHub Using SSH Key

Follow these steps to set up everything from cloning a repository in VS Code, creating an SSH key, and linking the SSH key to your GitHub account.

---

## **Step 1: Install Required Tools**
1. **Install Git:**
   - macOS usually comes with Git pre-installed. Verify by running:
     ```bash
     git --version
     ```
   - If not installed, install Git via [Homebrew](https://brew.sh/):
     ```bash
     brew install git
     ```

2. **Install VS Code:**
   - Download and install VS Code from [code.visualstudio.com](https://code.visualstudio.com/).

3. **Install GitHub CLI (Optional):**
   - Install GitHub CLI for easier GitHub management:
     ```bash
     brew install gh
     ```

---

## **Step 2: Sign In to VS Code**
1. Open VS Code and click on the **Accounts** icon in the bottom-left corner.
2. Select **Sign in with GitHub**.
3. Follow the on-screen instructions to authenticate with your GitHub account.

---

## **Step 3: Set Up SSH Key**
1. **Check If an SSH Key Already Exists:**
   - Run the following command in the Terminal to check if an SSH key exists:
     ```bash
     ls ~/.ssh/id_ed25519
     ```
   - If the file exists, skip to **Step 4**. Otherwise, generate a new SSH key.

2. **Generate a New SSH Key in the Terminal:**
   - Run the following command to generate a new SSH key:
     ```bash
     ssh-keygen -t ed25519 -C "your_email@example.com"
     ```
   - Replace `your_email@example.com` with the email address associated with your GitHub account.
   - Press `Enter` to accept the default file location and set a passphrase (optional).

3. **Add the SSH Key to the SSH Agent in the Terminal:**
   - Start the SSH agent:
     ```bash
     eval "$(ssh-agent -s)"
     ```
   - Add your SSH private key to the agent:
     ```bash
     ssh-add ~/.ssh/id_ed25519
     ```

---

## **Step 4: Add the SSH Key to GitHub**
1. **Copy the SSH Public Key:**
   - Run the following command in the Terminal to copy the SSH public key to your clipboard:
     ```bash
     pbcopy < ~/.ssh/id_ed25519.pub
     ```

2. **Add the Key to GitHub:**
   - Open a **browser** and go to **GitHub** → **Settings** → **SSH and GPG keys**.
   - Click **New SSH key**.
   - Paste the key and give it a title (e.g., "MacBook Air").
   - Click **Add SSH key**.

3. **Verify the SSH Connection in the Terminal:**
   - Test the connection to GitHub:
     ```bash
     ssh -T git@github.com
     ```
   - You should see a message like:
     ```
     Hi KeVinOoi0905! You've successfully authenticated, but GitHub does not provide shell access.
     ```

---

## **Step 5: Clone a Repository in VS Code**
1. **Copy the SSH URL of the Repository:**
   - Open a **browser**, go to the GitHub repository you want to clone, and click the green **Code** button.
   - Select **SSH** and copy the URL (e.g., `git@github.com:KeVinOoi0905/<repo>.git`).

2. **Clone the Repository Using VS Code:**
   - Open VS Code.
   - Open the Command Palette (`Cmd+Shift+P` or `Ctrl+Shift+P`).
   - Type `Git: Clone` and select it.
   - Paste the SSH URL when prompted.
   - Choose a folder on your MacBook Air to clone the repository into.

3. **Open the Repository:**
   - After cloning, VS Code will prompt you to open the repository.
   - Click **Open** to start working on the project.

---

## **Step 6: Make Changes and Push to GitHub**
1. **Pull the Latest Changes:**
   - Open the Terminal in **VS Code** or the macOS Terminal and run:
     ```bash
     git pull
     ```

2. **Make Changes:**
   - Edit files in your repository using VS Code.

3. **Stage and Commit Changes in the Terminal:**
   - Stage the changes:
     ```bash
     git add .
     ```
   - Commit the changes:
     ```bash
     git commit -m "Your commit message"
     ```

4. **Push Changes to GitHub:**
   - Push the changes:
     ```bash
     git push
     ```

---

## **Step 7: Optional - Configure Global Git Settings**
1. Set your name and email for Git globally in the Terminal:
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "your_email@example.com"
   ```

2. Verify your configuration:
   ```bash
   git config --list
   ```

---

## **Summary**
- Install Git, VS Code, and optionally GitHub CLI.
- Sign in to VS Code with your GitHub account.
- Generate and add an SSH key to GitHub.
- Use the SSH key to clone and work with repositories in VS Code.
- Make changes, commit, and push to keep your repository updated.

You’re now ready to manage your GitHub repositories seamlessly on your MacBook Air using VS Code!