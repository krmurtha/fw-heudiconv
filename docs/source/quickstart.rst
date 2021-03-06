********************************************
``fw-heudiconv`` Quick start guide
********************************************

Command Line
==============

1. Make sure you have the Flywheel `CLI <https://docs.flywheel.io/hc/en-us/articles/360008162214-Installing-the-Command-Line-Interface-CLI->`_ and `SDK <https://pypi.org/project/flywheel-sdk/>`_ installed. Note that this is ``flywheel-sdk`` and **NOT** ``flywheel``.

2. Download the package from pip with ``pip install fw-heudiconv``

3. Tabulate your DICOM header info with ``fw-heudiconv-tabulate --project <MY_PROJECT> --path <OUTPUT_PATH>``

4. Design your :ref:`heuristic <heuristic>` file in Python.

5. **Curate your dataset** on Flywheel into BIDS: ``fw-heudiconv-curate --project <MY_PROJECT> --heuristic <MY_HEURISTIC_FILE>``. Use the flag ``--dry_run`` to test your heuristic.

To **export the dataset** to your machine: ``fw-heudiconv-export --project <MY_PROJECT> --path <OUTPUT_DIR>``

Use the ``--subject <SUBJECT>`` and/or ``--session <SESSION>`` flags to use the tool on specific subject/session labels

Flywheel Gear
===============

1. Have the `Flywheel Heudiconv` gear installed on your Flywheel instance.

2. Design your heuristic file in Python and upload it to your project.

3. Run the `Flywheel Heudiconv` gear (accessible through `Run Gear -> Analysis Gear`), using your heuristic file as the input...

To **curate the dataset** into BIDS: In the "Gear Configuration" window, type "Curate" in the "Action" field, which will curate the dataset for BIDS. Click the "dry run" button to test your heuristic first (the gear log will print out all the changes without applying them).

To **export the dataset** into BIDS for downloading to your machine: In the "Gear Configuration" window, type "Export" in the "Action" field, which will leave an exported BIDS dataset in the gear's outputs. Click the "dry run" button to test your output first (the gear log will print out the expected directory structure of an export).

To **list the sequence information** for your dataset: In the "Gear Configuration" window, type "Tabulate" in the "Action" field, which will leave a sequence info table (.tsv) in the gear's outputs.
