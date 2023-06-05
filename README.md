# grammar_fixer_sentence_correction_python
Basic grammar fixer with sentence correction for Word files in Python
Explanation of the code:
1. We import the necessary modules:
   - `docx` module to work with Word documents.
   - `language_tool_python` module to access the LanguageTool library for grammar checking and suggestions.

2. The `fix_grammar` function is defined, which takes a paragraph as input and fixes the grammar errors in that paragraph.
   - The function initializes the LanguageTool object with the language code 'en-US' to indicate English.
   - The `check` method is called on the LanguageTool object to obtain a list of matches representing the grammar errors in the paragraph.
   - The function iterates over the matches in reverse order.
   - If a match has replacements available (i.e., suggestions to fix the error), the function extracts the start and end positions of the error and applies the first replacement suggestion to the paragraph.
   - Finally, the fixed paragraph text is returned.

3. The `fix_grammar_in_file` function is defined, which fixes the grammar in a Word file and saves it to a new file.
   - The function takes two parameters: `input_file` (the path to the input Word file) and `output_file` (the path for the output Word file).
   - The input Word file is loaded into a `doc` object using the `Document` class from the `docx` module.
   - A new `Document` object, `new_doc`, is created to store the fixed content.
   - The function iterates over each paragraph in the `doc` document.
   - For each paragraph, the `fix_grammar` function is called to fix grammar errors, and the fixed text is added as a new paragraph in the `new_doc` document.
   - Finally, the `new_doc` document is saved to the output file path.

4. The example usage section:
   - `input_file_path` and `output_file_path` variables are set to the paths of the input and output Word files, respectively. Replace these paths with the actual file paths you want to use.
   - The `fix_grammar_in_file` function is called with the input and output file paths as arguments to fix the grammar in the input file and save the result to the output file.

The code uses the `language_tool_python` library to fix grammar errors in each paragraph of a Word document and then saves the modified content to a new Word document.
