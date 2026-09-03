# -ENAI-Tag-Maker
ENAI Summer School Dubai 2026 - Tag Maker
A single-file web app: pick a name tag, add stickers, write your reflections, choose a Dubai photo, add your own photo (single or a 4-photo collage) and download the finished keepsake.

Publish on GitHub Pages
Create a repository and upload index.html to its root.
Repository Settings -> Pages.
Source: Deploy from a branch, Branch: main / root, then Save.
The app appears at https://<user>.github.io/<repo>/ within a minute or two.
Notes
Everything (fonts aside) is embedded in index.html - logos, stickers and the Dubai gallery photos are inlined, so there are no other files to upload.
Fonts load from Google Fonts and the image export uses html2canvas from cdnjs, so the page needs an internet connection.
Photos people add stay in their own browser; nothing is uploaded anywhere.
"Download" saves the keepsake as a PNG through the browser's normal download.
