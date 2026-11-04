# House style (single source of truth)

Version: 1.1
Based on: the Microsoft Writing Style Guide, with house decisions.
Used by: Doc planner (titles), Doc drafter (to write), and Style guide reviewer (to check).
Change a rule HERE, never in an agent's instructions.

## Voice and tone
1. Second person. Address the reader as "you."
   Bad: "The user should select the file."  Good: "Select the file."
2. Active voice, present tense.
   Bad: "The file will be saved by the system."  Good: "The system saves the file."
   A sentence that describes a UI state isn't passive.
   OK: "The check box is selected by default."
3. Contractions are encouraged.
   Bad: "You do not need to restart."  Good: "You don't need to restart."
4. No "we," "let us," or "let's" for the writer's voice.
   Bad: "Let us create a simple chart."  Good: "Create a simple chart."
5. No filler or condescension: "simply," "just," "easy," "obviously."
   Use "please" only when asking the reader to do something inconvenient.
   Bad: "It's simply a matter of following the steps."  Good: "Follow these steps."

## Headings
6. Sentence-style capitalization in titles and headings.
   Bad: "Configure Your Network Settings"  Good: "Configure your network settings"
7. Task headings start with a verb. No questions, no "How to."
   Bad: "How to uninstall?"  Good: "Uninstall Contoso Charts"
   Exception: a Troubleshooting title describes the symptom in the reader's
   words, and its section headings state causes.
   OK: "Charts don't update after editing Excel"

## Procedures and UI
8. UI actions: use "select" (not "click" or "click on"), "enter" (not "type in").
   Bold UI labels.
   Bad: "Click on the Save button."  Good: "Select **Save**."
9. One action per step. Say where before saying what.
   Bad: "Click Save on the File menu."  Good: "On the **File** menu, select **Save**."
   Standard dialog tasks count as ONE action. Don't split them.
   OK as one step: "In the **Save As** dialog box, choose a location and enter
   a file name."
10. Results aren't steps. Put a result in the same step, after the action.
    Bad: "4. Select **Install**. 5. The installation is indicated by a progress bar."
    Good: "4. Select **Install**. A progress bar shows the installation status."
11. No directional words for images or content: "above," "below," "as shown below."
    Bad: "Click Next as shown in the image below:"
    Good: "Select **Next**." (Place the image right after the step.)

## Word choice
12. Use "sign in" and "sign out," not "log in," "login," or "log out."
13. Bias-free language. Use "allow list/block list," "primary/replica,"
    and "they" or "you" instead of "he/she."
14. No Latin abbreviations: replace "e.g." with "for example," "i.e." with
    "that is," "via" with "through" or "by using." Avoid "etc."
15. Plain words: "use" not "utilize," "start" not "initiate,"
    "complete" or "fill in" not "fill up."
16. Word list: "email" (not "e-mail"); "double-click" (verb, hyphenated);
    "set up" (verb) vs. "setup" (noun).
    Bad: "Run the set up file."  Good: "Run the setup file."
17. "Might" for possibility, "can" for ability, "may" only for permission.
18. Versions: always name the product with a version number.
    Bad: "In version 4.2, ..."  Good: "In Contoso Charts 4.2, ..."

## Mechanics
19. Numbers: spell out zero through nine; use numerals for 10 and above.
    Technical values (versions, sizes, resolutions) always use numerals.
20. Serial (Oxford) comma: in a list of three or more items, put a comma
    before "and" or "or."
    Bad: "Select Name, Email and Phone."  Good: "Select Name, Email, and Phone."
21. Short sentences (aim for under 25 words). Put the key point first.
    If applying another rule leaves a sentence with no purpose, rewrite or
    delete it.
    Bad: "Contoso Charts provides an installation process."
    Good: "This article explains how to install and uninstall Contoso Charts."

## Accessibility
22. Every image needs alt text that describes what it shows.
    Bad: <img src="2.jpg">
    Good: <img src="2.jpg" alt="Setup wizard Welcome screen with the Next button">
23. Link text describes the destination. Never use "click here" or "here."
    Bad: "To know more on configuring the data grids click here."
    Good: "For more information, see Configure data grids."

## Shared markers (Doc drafter → Style guide reviewer)
- [S1], [S2] ... : source tags
- [GAP: ...] : missing information
- [CONFLICT: ...] : sources that disagree
