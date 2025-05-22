# Twine Project Template

A basic template for structuring a Twine project using the Twee plain text format and a compiler like Tweego.

## Story Format

This template is set up with a placeholder for **SugarCube 2.x.x**. You will need to:
1. Download the `format.js` file for SugarCube (or your desired format) from its official source.
2. Place it into the `storyformats/sugarcube-2/` directory (or a relevant subdirectory if using a different format).
   Alternatively, your Twee compiler might be able to fetch and use known story formats automatically.

## Directory Structure

- **`src/`**: Contains all your Twee source files (`.twee`), custom JavaScript (`javascript.js`), and custom CSS (`style.css`).
  - **`src/assets/`**: For images, audio, or other media files.
- **`dist/`**: The default output directory for the compiled HTML game file (e.g., `index.html`). This directory is ignored by Git.
- **`storyformats/`**: Holds story format files if you are not using a compiler's built-in versions.
  - **`storyformats/sugarcube-2/`**: Example directory for the SugarCube 2 format.
- **`.gitignore`**: Specifies files and directories to be ignored by Git.
- **`tweego_options.txt`**: Optional file to store Tweego build arguments.
- **`README.md`**: This file.

## How to Compile

You'll need a Twee compiler. [Tweego](https://www.motoslave.net/tweego/) is a popular command-line option.

**Basic Compilation Command (using Tweego):**

```bash
tweego -o dist/index.html --story-format=storyformats/sugarcube-2/format.js src/
```

This command tells Tweego:
- `-o dist/index.html`: Compile the story into `dist/index.html`.
- `--story-format=storyformats/sugarcube-2/format.js`: Use the specified story format file. (If your compiler handles formats differently or if the format is bundled, you might adjust or omit this).
- `src/`: Look for Twee source files, `javascript.js`, and `style.css` in the `src/` directory.

**Using `tweego_options.txt`:**

If you have defined your build settings in `tweego_options.txt` (see the example in that file), you can often compile more simply:

```bash
tweego @tweego_options.txt
```

## Dependencies

- A Twee compiler (e.g., Tweego).
- The story format file (e.g., SugarCube's `format.js`), unless your compiler fetches it.
