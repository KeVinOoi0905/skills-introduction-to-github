# Git Workflow Steps

1. **Create a new branch:**
   ```bash
   git branch <branch-name>
   ```
   - This creates a new branch where you can work on your changes.

2. **Edit the code:**
   - Make necessary changes to your code files.

3. **Save the code:**
   - Save your changes locally in your editor or IDE.

4. **Stage all changes for commit:**
   ```bash
   git add --all
   ```
   - This stages all modified, added, and deleted files for the next commit.

5. **Commit the staged changes:**
   ```bash
   git commit
   ```
   - This records your changes in the branch's history.

6. **Write a meaningful commit message:**
   - When prompted, provide a concise and descriptive message summarizing the changes.

7. **Push the branch to the remote repository:**
   ```bash
   git push
   ```
   - This uploads your branch to GitHub.  
   - **If this is the first time pushing the branch**, use:
     ```bash
     git push --set-upstream origin <branch-name>
     ```
     - This sets the upstream branch for future pushes and pulls.

8. **Switch back to the main branch:**
   ```bash
   git checkout main
   ```

9. **Merge the new branch into the main branch:**
   ```bash
   git merge <branch-name>
   ```
   - This integrates the changes from `<branch-name>` into the `main` branch.

10. **Ensure you are still on the main branch:**
    ```bash
    git checkout main
    ```

11. **Push the updated main branch to the remote repository:**
    ```bash
    git push
    ```
    - Updates the remote repository with the latest changes from the `main` branch.

12. **Reset your branch to match the remote branch:**
    ```bash
    git reset --hard origin/<branch-name>
    ```
    - This discards local changes and updates your branch to match the remote branch exactly.

13. **Undo the last commit (if needed):**
    ```bash
    git reset --soft HEAD~1
    ```
    - This undoes the last commit but keeps your changes staged for editing or recommitting.