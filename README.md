# Aiden Seay — Resume Website

A static webpage that displays the general resume by default and lets visitors switch to the federal resume. Open and Download buttons always use the selected document. No framework, dependencies, or build step are required.

## Files

Keep these four files together at the repository root:

| File | Purpose |
| --- | --- |
| `index.html` | Webpage, styling, and resume-switching script |
| `resume.pdf` | General professional resume (default view) |
| `federal-resume.pdf` | Federal resume |
| `README.md` | Setup and maintenance instructions |

Replace your existing `index.html` and `README.md` with these versions. Keep your two PDFs with the exact names above. Filenames are case-sensitive on GitHub Pages. Use one README, rather than keeping both `README.md` and `readme.md`.

## Run locally for testing

1. Open a terminal in the folder containing the four files. For example, use your file manager's **Open in Terminal** command, or run `cd /path/to/your/repository` with your actual path.
2. Check that Python 3 is available:

   ```bash
   python3 --version
   ```

3. Start a local web server from that folder:

   ```bash
   python3 -m http.server 8000 --bind 127.0.0.1
   ```

4. Keep that terminal open and visit [http://localhost:8000](http://localhost:8000).
5. Check that the general resume appears first. Click **View Federal Resume**, then **Resume**, and confirm that **Open PDF** and **Download resume** use the selected PDF. Check the layout in a narrow browser window too.
6. Edit `index.html`, save it, and refresh the browser to see changes. No rebuild is needed.
7. Press **Ctrl+C** in the terminal to stop the server.

On Windows, you can use `py -m http.server 8000 --bind 127.0.0.1` instead. If port 8000 is already in use, change it to 8001 and visit `http://localhost:8001`.

Some browsers do not embed PDFs, particularly on mobile. The Open PDF and Download buttons provide direct access. If JavaScript is disabled, the resume-selection links open the PDFs directly.

## Deploy on GitHub Pages

1. Open your existing GitHub repository, or create a public repository (for example, `resume`). Public repositories support Pages on GitHub Free.
2. Commit all four files to the repository root on your publishing branch. To upload through GitHub, use **Add file → Upload files**, select the files themselves, and commit the changes. Do not upload a ZIP or place the files inside an extra folder.
3. Open the repository's **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select your branch (usually `main`) and **/(root)**, then click **Save**.
6. Check the repository's **Actions** tab for deployment progress. Once complete, **Settings → Pages** provides the published address.

For a repository named `resume` under `aidengseay`, the address is [https://aidengseay.github.io/resume/](https://aidengseay.github.io/resume/). If your repository is named `federal-resume`, it is [https://aidengseay.github.io/federal-resume/](https://aidengseay.github.io/federal-resume/). Use the address GitHub shows for your actual repository.

See [GitHub's official publishing instructions](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

## Publish updates

Replace the relevant PDF while keeping its filename. Commit and push to the configured publishing branch; Pages republishes automatically. No HTML changes are needed when only the PDFs change.

If your local folder is already a Git checkout connected to GitHub, run these commands from its root after testing:

```bash
git status
git add index.html README.md resume.pdf federal-resume.pdf
git commit -m "Update resume website"
git push
```

This assumes your current branch is the configured publishing branch and has its upstream set. You can also upload replacement files through GitHub's website.

## Troubleshooting

- **Website returns 404:** Confirm deployment succeeded, the publishing folder is `/(root)`, and `index.html` is at that root. Use the URL shown in Pages settings.
- **PDF is missing:** Check exact spelling and case of `resume.pdf` and `federal-resume.pdf`, and confirm both were committed at the same level as `index.html`.
- **PDF does not display inline:** Use Open PDF. Browser PDF support varies.
- **Old content remains:** Wait for deployment to complete, then hard-refresh or open a private browser window.
- **Local page lists files instead:** Start the server from the directory containing `index.html`.

## Customize

Edit the `<style>` section in `index.html` to change colors and spacing. Contact links are in the header. The `resumes` object in the script maps each selection to its PDF. If renaming PDFs, update both the HTML links and script paths. Keep the `./` relative paths so links work under a GitHub Pages project URL.
