# Upload this project to GitHub

Suggested repository name: **vibe-analysis-powerbi-dashboard**

Suggested description:

> E-commerce sales and profit analysis using Power BI, Power Query, DAX and a star schema, with data cleaning and interactive filters.

Suggested topics: `powerbi`, `dax`, `power-query`, `data-analysis`, `data-visualization`, `star-schema`, `ecommerce`, `portfolio`.

## Browser upload

1. Extract the supplied package.
2. Visit https://github.com/new and create a repository named `vibe-analysis-powerbi-dashboard`. Choose Public if you want recruiters and other visitors to see it.
3. The package already contains a README; you can leave the new-repository README option unchecked.
4. In the new repository, select **uploading an existing file**, or **Add file → Upload files**.
5. Open the extracted `vibe-analysis-powerbi-dashboard` folder. Drag its contents into GitHub, preserving the folder structure. Upload the contents, not just the ZIP and not the enclosing folder, so README.md is at repository root.
6. Check that `README.md`, `screenshots/`, `powerbi/`, `data/` and `docs/` are included. Keep the complete Power BI folder, including its item metadata.
7. Use the commit message **Add Vibe Analysis Power BI portfolio project**, then commit the upload.
8. Visit the repository home page and confirm both preview images load in the README.
9. Add the description and topics under the repository's About settings.

The package is below GitHub's browser limit of 25 MiB per file and contains fewer than 100 files.

## Optional: upload with Git in the VS Code terminal

Open the extracted project folder in VS Code and run:

```bash
git init
git add .
git commit -m "Add Vibe Analysis Power BI portfolio project"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/vibe-analysis-powerbi-dashboard.git
git push -u origin main
```

Replace `YOUR_USERNAME` with your GitHub username. These commands assume a new local project and an empty GitHub repository. Authenticate through Git's normal sign-in flow if prompted.

## What visitors can see

GitHub displays the README, screenshot previews, data and source files. Power BI slicers run in Power BI Desktop or a separately hosted Power BI report, not inside a README screenshot. No public interactive report has been published as part of this package.

Official references:
- https://docs.github.com/en/repositories/creating-and-managing-repositories/quickstart-for-repositories
- https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository
- https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes
