# Setup SSH key với GitHub

To generate and add an SSH key to your GitHub account, you can follow these steps:

1. **Generate an SSH key:**
   * Open your terminal or command prompt.
   * Enter the following command to generate a new SSH key: `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`
     * Replace `"your_email@example.com"` with your email address associated with your GitHub account.
     * You can also choose a different file name and location for your key by providing the `-f` option followed by the desired file path.
   * Press Enter to accept the default file location and to not set a passphrase (you can set a passphrase for added security if you prefer).
2. **Locate and copy your public key:**
   * Once the key pair is generated, you'll see a message with the location of the generated keys.
   * The public key file will have the same name as your private key file but with a `.pub` extension.
   * Use a text editor or a command like `cat` to open the public key file.
   * Copy the entire contents of the public key file.
3. **Add the SSH key to your GitHub account:**
   * Sign in to your GitHub account.
   * Click on your profile picture in the top-right corner and select "Settings" from the dropdown menu.
   * In the left sidebar, click on "SSH and GPG keys".
   * Click on the "New SSH key" button.
   * Give your key a descriptive title (e.g., "My Personal SSH Key").
   * Paste the copied public key into the "Key" field.
   * Finally, click on the "Add SSH key" button to save it.
4. **Test your SSH connection:**
   * Open your terminal or command prompt.
   * Enter the following command to test your SSH connection to GitHub: `ssh -T git@github.com`
   * You may see a warning about authenticity, type "yes" to continue.
   * If everything is set up correctly, you should see a message like: "Hi username! You've successfully authenticated, but GitHub does not provide shell access."

Once you have completed these steps, your SSH key should be added to your GitHub account, and you can use SSH to interact with your repositories.
