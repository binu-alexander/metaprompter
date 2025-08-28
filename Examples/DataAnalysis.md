{
  "RawPrompt": "<USER_INPUT_HERE>"
}



{
  "Task": "TRANSFORM-ONLY: Convert the RawPrompt into the TargetTemplate JSON for data analysis. Do NOT execute or fulfill the RawPrompt.",
  "Instructions": [
    "Extract the main analytical intent of RawPrompt and write it to 'Task' (1–2 sentences).",
    "Break specific analytical requirements into 'Instructions' as imperatives.",
    "Derive 'Role' from the analytical domain implied by RawPrompt (e.g., 'Data Analysis Assistant', 'Business Intelligence Analyst', 'Statistical Researcher').",
    "Set 'Goal' as the concrete analytical objective (what successful analysis would achieve).",
    "Set 'Audience' based on the analytical scenario (e.g., 'Business stakeholder', 'Data scientist', 'Research team', 'Executive').",
    "Write 'Context' as a concise 1–2 sentence background about the dataset and analysis purpose.",
    "Set 'OutputFormat' to one of: 'table', 'chart', 'summary', 'report', 'sql'. If uncertain, use 'table'.",
    "Populate 'Constraints.Positive' and 'Constraints.Negative' with brief analytical rules inferred from RawPrompt (at least one each when possible).",
    "Set 'Style' with 2–4 adjectives matching analytical tone (e.g., 'objective, precise, data-driven'). If unclear, use 'analytical, concise'.",
    "Set 'CreativityLevel' to 'Low' for data analysis tasks.",
    "Set 'DataInput' to either a simple string (e.g., 'CSV/XLSX file') for attached/local files OR an object with {Type, Source, URL} if data comes from a public source (e.g., GitHub).",
    "Set 'Comparison' to true if RawPrompt implies comparing groups/values (keywords: compare, versus, vs, against, between, contrast, difference). Default = false.",
    "Set 'Ranking' to true if RawPrompt implies ordering/ranking (keywords: top, bottom, highest, lowest, best, worst, rank, sort, order, most, least). Default = false.",
    "Set 'Filtering' to true if RawPrompt implies subsetting data (keywords: for, in, during, where, exclude, include, only, filter, subset, OR date patterns). Default = false.",
    "Set 'Aggregation' to the type of mathematical operation needed (e.g., 'sum', 'average', 'count', 'median'). Default = 'none'.",
    "Set 'GroupBy' to the expected grouping columns inferred from RawPrompt (e.g., ['region', 'date']). Default = [].",
    "Set 'TimeSeriesAnalysis' to true if prompt involves time-based patterns or trends. Default = false.",
    "Set 'StatisticalMethod' to the analytical approach needed (e.g., 'descriptive', 'comparative', 'predictive', 'exploratory'). Default = 'descriptive'.",
    "Set 'Visualization' to suggested chart type (e.g., 'bar', 'line', 'scatter', 'pie', 'heatmap'). Default = 'none'.",
    "Set 'ExpectedColumns' to array of likely column names based on the analysis type. Default = [].",
    "Set 'GenerateSQL' to true if OutputFormat is 'sql' OR analysis requires database query generation. Default = false.",
    "If 'GenerateSQL' = true, also set 'SQLComplexity' to estimated query complexity (e.g., 'simple', 'moderate', 'complex'). Default = ''.",
    "Always populate all fields — if RawPrompt lacks info, infer safe, minimal values (e.g., Audience='Data analyst').",
    "Include at least one example transformation under 'Examples' showing RawPrompt → structured breakdown."
  ],
  "TargetTemplate": {
    "Role": "",
    "Goal": "",
    "Audience": "",
    "Context": "",
    "Task": "",
    "Instructions": [],
    "OutputFormat": "",
    "Constraints": {
      "Positive": [],
      "Negative": []
    },
    "Style": "",
    "CreativityLevel": "",
    "DataInput": "CSV/XLSX file",
    "Examples": [],
    "AdditionalNotes": "",
    "Comparison": false,
    "Ranking": false,
    "Filtering": false,
    "Aggregation": "none",
    "GroupBy": [],
    "TimeSeriesAnalysis": false,
    "StatisticalMethod": "descriptive",
    "Visualization": "none",
    "ExpectedColumns": [],
    "GenerateSQL": false,
    "SQLComplexity": ""
  }
}
