# Clone your repo locally
git clone https://github.com/dhorton77/Lab-reports-.git
cd Lab-reports-

# Create the folder structure
mkdir SSH-Brute-Force-Reports
mkdir Lab-Infrastructure

# Move existing files into folders
mv Wazuh_SSH_Lab_Report*.docx SSH-Brute-Force-Reports/
mv Lab_Reports_Non_Technical*.docx SSH-Brute-Force-Reports/
mv Splunk_Supplementary_SIEM_Report_FINAL.docx SSH-Brute-Force-Reports/

# Stage all changes
git add .

# Commit
git commit -m "Reorganize reports into folder structure"

# Push to GitHub
git push origin main
