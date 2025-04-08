# Exporting Power BI Semantic Model Lineage into CSV Files

*Date: April 2, 2025*  
*Tags: Power BI, CLI, Python, Lineage, Data Source*  
*Category: Power BI Scripts*

## Why Export Semantic Model Lineage?

Understanding the lineage of your Power BI semantic models, specifically, which data sources are being used and how they connect to your models, can be incredibly useful in a variety of scenarios:

1. **Governance & Compliance**: Ensure that sensitive or regulated datasets are only being used in approved reports or dashboards.
2. **Impact Analysis**: Identify which reports or datasets might be impacted if a data source changes, enabling proactive updates and minimizing downtime.
3. **Optimization**: Spot underused or redundant data sources that can be optimized or consolidated.
4. **Documentation**: Maintain up-to-date documentation of your data ecosystem for internal knowledge sharing and onboarding.

To make this process easier, I've created a Python script that extracts the semantic model lineage from Power BI and exports it into CSV files for further analysis.


## The Solution

The script I created, [`inventory-cli.py`](https://github.com/viktorradu/fabric-datasource-inventory/blob/main/inventory-cli.py), leverages the Power BI REST API to extract metadata about your datasets, models, and their associated data sources. It then organizes this information into a CSV file for easy review.

### Running the Script in CLI

Follow these steps to use the script in your environment:

1. **Clone the Repository**  
   First, clone the GitHub repository to your local machine:
   ```bash
   git clone https://github.com/viktorradu/fabric-datasource-inventory.git
   cd fabric-datasource-inventory
   ```

2. **Install Dependencies**  
   The script relies on Python 3 and some additional libraries. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. **Configure Authentication**  
   You'll need a Fabric Administrator user account or a service principal with the necessary API permissions. When using a service principal, make sure to provide --tenant, --client, and --secret arguments when running the script.

4. **Run the Script**  
   Execute the script using the following command:
   ```bash
   python inventory-cli.py --output output
   ```

   The script will connect to your Power BI tenant, query the metadata, and save the lineage information into the output folder.


## Example Output

The exported CSV files will contain columns such as:

- Semantic model name
- Workspace name
- Datasource Type (e.g., SQL Server, Azure Storage, etc.)
- Connection Details (e.g. servers, databases, file paths, etc.)

This structured output makes it easy to analyze and filter the lineage data as needed.



## GitHub Repository

You can find the script and additional documentation in the GitHub repository:  
[https://github.com/viktorradu/fabric-datasource-inventory](https://github.com/viktorradu/fabric-datasource-inventory)



## Conclusion

Exporting semantic model lineage is a key step in maintaining a well-documented and governed Power BI environment. Whether you're preparing for compliance audits, performing impact analysis, or simply trying to optimize your data ecosystem, this script can save you time and effort.

Have questions or feedback? Feel free to reach out or submit an issue on the GitHub repository. Happy analyzing!