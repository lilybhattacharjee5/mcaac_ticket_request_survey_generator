# MCAAC Ticket Request Survey Generator

**Dependencies**: Python >=3.6.10, libraries: pandas, json, datetime

## Getting Started
To run the event survey generator script and create a Qualtrics survey to streamline MCAAC committee member ticket request submissions, the required input is an Excel file with the following columns (not named in the header, following the format [linked](https://github.com/lilybhattacharjee5/mcaac_ticket_request_survey_generator/blob/master/Mondavi%20Center%20Spring%20Quarter%20Events%20for%20MCAAC.xlsx) in this repo): "event name", "date", "time", "link", "notes". This can be refactored in the script if the input changes (see lines [9-16](https://github.com/lilybhattacharjee5/mcaac_ticket_request_survey_generator/blob/ce1b12b323af0c5a468626d11a1d4f44127d348b/event_survey_generator.py#L9), which parses the file and extracts the relevant data).

<img width="1136" alt="Screen Shot 2022-03-02 at 3 30 30 PM" src="https://user-images.githubusercontent.com/14793917/156467228-512d7889-9a1b-45a9-8b03-7aed76320220.png">

After cloning, in the terminal inside the working directory of the repo, run the following:

```
python3 event_survey_generator.py [event info file]
```

The script will generate a QSF file named "Mondavi Center Spring Quarter Events for MCAAC.qsf" (or "name.qsf", depending on the name specified in the script at line [6](https://github.com/lilybhattacharjee5/mcaac_ticket_request_survey_generator/blob/ce1b12b323af0c5a468626d11a1d4f44127d348b/event_survey_generator.py#L6)).

Upload the QSF file to Qualtrics by accessing "Tools" > "Import / Export" > "Import Survey." This will generate a new Qualtrics survey project corresponding to the inputs provided:

<img width="400" alt="Screen Shot 2022-03-02 at 3 34 54 PM" src="https://user-images.githubusercontent.com/14793917/156467768-7c8f41ce-c0c6-494b-ab4c-2e20519d0328.png">

The current UI of the survey follows the format:
- *page 1*: required information collected per user (name, email, accessibility)

<img width="400" alt="Screen Shot 2022-03-02 at 3 38 33 PM" src="https://user-images.githubusercontent.com/14793917/156468106-181401d4-8ce4-4210-a989-19273cf47a4e.png">

- *page 2*: select events of interest, request tickets per event

<img width="400" alt="Screen Shot 2022-03-02 at 3 38 51 PM" src="https://user-images.githubusercontent.com/14793917/156468123-a73d89ad-a678-4619-91b4-5377972b857a.png">

- *page 3*: rank events by priority

<img width="400" alt="Screen Shot 2022-03-02 at 3 39 03 PM" src="https://user-images.githubusercontent.com/14793917/156468140-fba4a4a2-ce43-4f7e-b9e7-91b4e225ef4a.png">

The setup currently sends a confirmation email with user response values upon survey submission.
