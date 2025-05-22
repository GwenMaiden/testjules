# Workflow

Write your story: Create and edit .twee files in the src/ directory.
Compile: Use your chosen Twee compiler (e.g., Tweego) to build the HTML file.
Example command: tweego -o dist/index.html --format=sugarcube-2 src/
If using local story formats: tweego -o dist/index.html --story-format=storyformats/sugarcube-2/format.js src/
Test: Open the generated dist/index.html in your browser.
Commit:
Commit changes to your Twee source files (src/), any new assets, and updates to your README.md or build scripts.
Do not commit the dist/ folder if it's in your .gitignore (recommended for development branches).
Push: Push your committed changes to GitHub.

# Special Twee Passages

Leverage Twee 3 specific passages in your .twee files:

:: StoryTitle: Sets the title of your game.
Code snippet
```twee
:: StoryTitle
My Awesome Adventure
```

:: StoryData: Contains JSON data with important metadata, including the IFID (Interactive Fiction Identifier) and story format. Most compilers will generate an IFID if one isn't present.
Code snippet
```json
:: StoryData
{
    "ifid": "YOUR-UNIQUE-IFID-HERE-GET-ONE-FROM-A-UUID-GENERATOR",
    "format": "SugarCube",
    "format-version": "2.36.1",
    "zoom": 1
}
```
It's good practice to generate a UUID (Version 4) for your IFID.

# Publishing to GitHub Pages

For sharing your game, GitHub Pages is an excellent option:

Compile your game to a file named index.html (or ensure your main HTML file is index.html).
Push to gh-pages branch:
The simplest method is to have a separate branch (commonly named gh-pages) where you do commit the compiled index.html file (and any assets it needs, like images or CSS, if they are not embedded).
You can manually copy the contents of your dist/ folder to the root of your gh-pages branch and commit there.
Alternatively, if your dist folder contains everything needed, you can use commands like git subtree push --prefix dist origin gh-pages or use GitHub Actions.
Enable GitHub Pages: In your repository settings under "Pages," select the gh-pages branch (and the /root folder) as the source. Your game will then be available at your-username.github.io/your-repository-name/.

# Advanced: Automation with GitHub Actions

For a more streamlined process, you can set up GitHub Actions to automatically compile your Twee source and deploy it to GitHub Pages whenever you push changes to your main branch.

Create a workflow file (e.g., .github/workflows/deploy.yml).
This workflow would:
Check out your code.
Set up your Twee compiler (e.g., download Tweego).
Run the compilation command.
Deploy the contents of the dist/ folder to the gh-pages branch.
This setup provides a robust, version-controlled, and potentially automated environment for developing your Twine games using Twee. Remember to consult the documentation for your specific Twee compiler and story format for more detailed options.
