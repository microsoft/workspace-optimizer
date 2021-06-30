# Workspace Collaboration Optimizer

If your team or company is moving to a new worksite or you need to reorganize an existing workspace, this open-source tool can help. Workspace planning can help you identify and seat teams together in a workspace that maximizes and fosters cross-team productivity and collaboration. You can use this tool to generate seating plans quickly and objectively, in a data-driven way that optimizes employee collaboration by seating teams together.

The algorithm for this tool accounts for the following rules and constraints:

* **Teams stay together** - When a workspace can seat everyone on the team, it will keep them all together.
* **Teams who collaborate the most sit together** - Based on the collaboration patterns and the distances between spaces, if team A spends most of its time with team B, the two teams are assigned workspaces that are as close together as possible.
* **The most central team is in the most central workspace** - As lower priority than the previous two, the tool can help you determine which floor plans are better than others for seating specific teams in central locations.
* **Everyone gets a seat** - All team members get an assigned seat in a workspace.
* **People and seat assignments must match** - No workspace is assigned more people than it has seats for, and no workspace can have a negative number of people assigned to seats.

You can create seating plans that require different variables, such as the following:

* Co-locate teams who collaborate the most with each other within the same multi-floored building that has multiple zones or neighborhoods.
* Cross-team collaboration around constraints for specific teams. For example, the HR team must be located together on the first floor in the same neighborhood and Zone A must be next to the file room.
* Create seating for alternating or rotating work schedules for teams who share a workspace on different weeks or days.

## Prerequisites

Before you can use the tool, confirm the following required prerequisites are met.

* **Anaconda** - Use to install and manage the following required versions of Python and Jupyter Notebook. See [Anaconda](https://www.anaconda.com/products/individual#windows) to install it. During the installation, select to **Register Anaconda as your default for Python**.
* **Python** - Latest available or version 3.3 or later is required.
* **Jupyter Notebook** - An open-source application that's required to run the Workspace planning tool.
* **Workplace Analytics** - Have [the app set up](https://docs.microsoft.com/workplace-analytics/setup/set-up-workplace-analytics.md) with an analyst role to create the query data for the interaction file.

## File prep

Save the following files to a **master folder**, which are located in the [Workspace Collaboration Optimizer repository](https://github.com/microsoft/workspaces-optimizer). If you’re new to GitHub, you’ll need to register and sign in before you can access this repository. See [GitHub Getting started](https://docs.github.com/github/getting-started-with-github) for details.  You'll use this master folder to create a copy of for each workspace project.

* **Distance Helper notebook** - Creates a distance file between specified zones or neighborhoods. This uses the following input files to help you define the walking distances in a unit you specify, such as estimated minutes or meters between floors or buildings.
* **File Validations notebook** - Validates all the input files, including the distance file that's created from the Distance helper notebook.
* **Generate Floorplan notebook** - Creates a floor plan from the validated input files and reruns the algorithm on the floor plan.
* **Requirements text file** - Includes the list of Python packages needed to run the notebooks.

### Input files

You also need to save the following input (.csv) files to your master folder. These files define the relevant information for each workspace project, such as team sizes and workspace capacity. The tool uses these to generate the floor plans with recommended seating for each team based on their collaboration patterns from the interaction file.

* [Interaction](https://docs.microsoft.com/workplace-analytics/azure-templates/space-planning#create-an-interaction-file) - This is a Workplace Analytics group-to-group query that shows current work and collaboration patterns across the different teams.
* [Team size](https://docs.microsoft.com/workplace-analytics/azure-templates/space-planning#create-a-team-size-file) - Defines the number of employees in each team in your organization.
* [Space capacity](https://docs.microsoft.com/workplace-analytics/azure-templates/space-planning#create-a-space-capacity-file) - Defines the workspace, which can be a combination of buildings, floors, and zones or neighborhoods, and the maximum capacities for each.

The tool combines the data in these files to generate a table that shows where to seat people in the specified floor plan.

See [Workspace planning tool](https://docs.microsoft.com/workplace-analytics/use/wsplan) for detailed instructions on how to install and plan a workspace.

# Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

# Support

## How to file issues and get help  

This project uses GitHub Issues to track bugs, feature requests, and questions. Please search the existing 
issues before filing new issues to avoid duplicates. For new issues, file your bug or 
feature request as a new Issue.

For help and questions about using this project, please submit your questions via Github Issues.

## Microsoft Support Policy  

Support for this project is limited to the resources listed above.

# Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft 
trademarks or logos is subject to and must follow 
[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general).
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.
