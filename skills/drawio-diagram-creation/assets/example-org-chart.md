# Example: Organization Chart (CSV)

This is a template for creating organizational charts using CSV format in draw.io.

## CSV Format

The CSV format for org charts follows this structure:
- **Column 1**: Employee/Position Name
- **Column 2**: Reports To (manager/parent)
- **Column 3**: Department
- **Column 4**: Title/Role

Leave the "Reports To" field empty for the top-level position (CEO/Director).

## Example CSV Data

```csv
Name,Reports To,Department,Title
Alice Johnson,,Executive,Chief Executive Officer
Bob Smith,Alice Johnson,Technology,Chief Technology Officer
Carol Davis,Alice Johnson,Finance,Chief Financial Officer
David Lee,Alice Johnson,Marketing,Chief Marketing Officer
Emma Wilson,Bob Smith,Engineering,VP of Engineering
Frank Brown,Bob Smith,IT Operations,VP of IT Operations
Grace Taylor,Carol Davis,Finance,Finance Manager
Henry Martinez,David Lee,Marketing,Marketing Manager
Ivy Anderson,Emma Wilson,Engineering,Engineering Manager - Platform
Jack Thomas,Emma Wilson,Engineering,Engineering Manager - Product
Karen White,Frank Brown,IT Operations,DevOps Manager
Laura Harris,Grace Taylor,Finance,Senior Accountant
Michael Clark,Henry Martinez,Marketing,Marketing Specialist
Nancy Lewis,Ivy Anderson,Engineering,Senior Software Engineer
Oscar Walker,Ivy Anderson,Engineering,Software Engineer
Paula Hall,Jack Thomas,Engineering,Senior Software Engineer
Quinn Young,Jack Thomas,Engineering,Software Engineer
Rachel Allen,Karen White,IT Operations,DevOps Engineer
Steve King,Karen White,IT Operations,Systems Administrator
```

## To Use This Template

1. Copy the CSV content above or create your own
2. Modify the data to match your organization
3. Use the draw.io MCP tool: `open_drawio_csv`
4. The diagram will automatically generate the hierarchical structure
5. Customize colors, shapes, and layout in draw.io
6. Export as needed

## Tips for CSV Org Charts

- Keep names consistent between "Name" and "Reports To" columns
- Use the same spelling and capitalization
- Add additional columns for phone, email, or location if needed
- Ensure each person has at most one manager (no circular reporting)
- Group by department for better visual organization
