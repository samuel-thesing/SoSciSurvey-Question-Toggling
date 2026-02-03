# Selection-Based Same-Page Question-Toggling

Available for three types of questions:
- Dropdown (toggleQuestionbyDropdown)
- Multi-Select (toggleQuestionbyMultiSelect)
- Single-Select (toggleQuestionbySingleSelect)

<br>
All of these functions expect the same arguments:

1. Question whose options should toggle other questions (The name for the questions can be found using 'Inspect')
2. List of labels of the question from 1. where the questions from 3. should be shown
3. List of questions to toggle
4. Optional: Callback with single bool-argument. If the questions are shown true else false


## Examples
```js
toggleQuestionByDropdown("AB01", ["Anderer"], ["AB35_qst"]);
toggleQuestionByMultiSelect("AB04_qst", ["DZG (mit Folgefrage)"], ["AB05_qst"]);
toggleQuestionBySingleSelect("AB05_qst", ["DZG (mit Folgefrage)"], ["AB05_qst"]);

// The following code shows an example usage of the callback,
// where the input-field of the toggled question is cleared if it is hidden.
toggleQuestionByDropdown("AB01", ["Anderer"], ["AB35_qst"], (show) => {
    if (!show) {
        ab35Input.value = "";
    }
});
```