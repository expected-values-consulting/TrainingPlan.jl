# TrainingPlan

[![Stable](https://img.shields.io/badge/docs-stable-blue.svg)](https://fieldofnodes.github.io/TrainingPlan.jl/stable/)
[![Dev](https://img.shields.io/badge/docs-dev-blue.svg)](https://fieldofnodes.github.io/TrainingPlan.jl/dev/)
[![Build Status](https://github.com/fieldofnodes/TrainingPlan.jl/actions/workflows/CI.yml/badge.svg?branch=main)](https://github.com/fieldofnodes/TrainingPlan.jl/actions/workflows/CI.yml?query=branch%3Amain)

# TrainingPlan

Welcome to the `TrainingPlan` module! This Julia package is designed to facilitate the creation and management of training plans, particularly for generating well-structured tables in LaTeX format. It builds upon the `TrainingContent` module to create detailed training tables, which can be exported to LaTeX documents.

## Features

- **Table Generation**: Create training tables with week indices, content types, and titles formatted for LaTeX.
- **Export to File**: Easily write the generated LaTeX table to a file for integration into your documents.
- **Customizable Layout**: The module provides functions to generate headers, rows, and footers, enabling customization of the table format.

## Installation

To use `TrainingPlan`, ensure that you have Julia installed on your system. You can add this module to your Julia environment by including it in your project or environment:

```julia
] add https://github.com/your-repo/TrainingPlan
```

## Usage

Begin by importing the module into your Julia environment:

```julia
using TrainingPlan
```

### Generating a Training Table

To generate a LaTeX-formatted training table from a `TrainingTableData` object, use the `generate_table` function:

```julia
training_table = generate_table(ttd::TrainingTableData)
```

This function creates a LaTeX table that includes:

- **Header**: A formatted header using `generate_table_header`.
- **Rows**: Each row corresponds to a week, content type, and content title.
- **Footer**: A formatted footer using `generate_table_footer`.

### Writing the Table to a File

Once the table is generated, you can write it to a file using the `write_table_to_file` function:

```julia
write_table_to_file("training_table.tex", ttd::TrainingTableData)
```

This will create a `.tex` file with the generated table content, ready to be included in a LaTeX document.

### Example Usage

```julia
# Assuming you have already generated `TrainingTableData` from the TrainingContent module
using TrainingContent

# Create some sample content titles
titles = ["Introduction", "Module 1: Basics", "Module 2: Advanced Topics"]

# Generate the training table data
training_data = generate_TrainingTableData(titles; course_length=10)

# Generate the LaTeX table as a string
latex_table = generate_table(training_data)

# Write the LaTeX table to a file
write_table_to_file("my_training_plan.tex", training_data)
```

### Customizing the Table Layout

If you need to customize the appearance of the table further, you can modify the `generate_table_header`, `generate_table_row`, and `generate_table_footer` functions to suit your specific formatting requirements.

## Contributing

Contributions to `TrainingPlan` are welcome! Please submit a pull request with your changes or open an issue if you encounter any problems.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

For questions, suggestions, or feedback, feel free to reach out via [GitHub Issues](https://github.com/your-repo/TrainingPlan/issues).

---

This README provides an overview of the functionality within `TrainingPlan`. For detailed examples and additional information, please refer to the module's source code and documentation.
