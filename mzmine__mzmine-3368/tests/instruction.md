# Issue

**Title:** Extensions to integration dashboard

## Description

Dear MZmine team

Thank you for the great software!

I liked the new Integration Dashboard feature quite a lot to quickly review processing results with a focus on peak being continuously detected and wanted to extend it a bit: 
- I did not use the controls at all, and the axis titles used a lot of valuable space on the monitors
- It was also difficult to get to the names of the samples, where detections did not occur

Thus, I have extended the dashboard a bit. This pull request includes some additional controls to
- allow the user to toggle the file-name, axis titles, and the controls (to get more space on the display)
- color the chart by the sample/group colors defined for each sample/group (to see if there are systematic effects)
- sort the charts by detected peak area (added to the already existing "Sort files by" combo box
- have the crosshair synchronized among plots to easily inspect retention times and intensity values there (this does not change the controls' behavior though)

Please find here some screenshots (Figures 1-3) showing the changes. 

Figure 1 | Changes: 1) Additional controls to show/hide file-names, integration controls, axis titles, and to color the samples identically (black line and yellow area as show) or in the samples' colors; 2) new title showing the sample name, 3) controls are now also shown in the sample color, 4) axis titles currently shown, 5) new sort options
<img width="1755" height="1040" alt="fig1" src="https://github.com/user-attachments/assets/fcdf5a8d-2cc6-482a-99fd-5801fd361264" />

Figure 2 | Changes: Now no title, axis titles or controls are shown and the lines and peak areas are colored according to the samples' colors defined in the tab "MS data files"
<img width="1755" height="1040" alt="fig2" src="https://github.com/user-attachments/assets/923b2730-7a64-4051-8d88-fd8fa2df4cdd" />

Figure 3 | Samples are resorted by the area of the detected peaks (min to max) with the crosshair selecting a particular retention time and intensity value, which is shown in all plots likewise and allows to see that the last samples is much more abundant than one of the first ones. 
<img width="1755" height="1040" alt="fig3" src="https://github.com/user-attachments/assets/7e91e94b-dc47-4aa8-b9ab-ea94bb874ee0" />

If you think that these changes might be beneficial also to other user, I would be thankful for any feedback of yours and ideas on how to further extend this great dashboard. 

Implemented code and work: 
- The initial code for these changes was implemented by the LLM Claude/Sonnect 4.6 with GitHub CoPilot
- All code was manually checked and adapted by the submitter
- All implemented and changed sourcce files were re-formatted
- The functionality was tested extensively (manually, no automated tests have been added)

Best regards, christoph

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `b3a5eb1e0090`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.