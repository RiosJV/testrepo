def clean_and_compare(df, dfFileName, filePath, uat_suffix="_uat", prod_suffix="_prod"):
    try:
        comparison_results = {}

        for col in df.columns:
            if col.endswith(uat_suffix):
                base_col = col[:-len(uat_suffix)]
                prod_col = f"{base_col}{prod_suffix}"
                
                if prod_col in df.columns:

                    uat_numeric = pd.to_numeric(df[col], errors='coerce')
                    prod_numeric = pd.to_numeric(df[prod_col], errors='coerce')
                    
                    comparison_key = f"{base_col}_comparison"
                    result = []
                    
                    for uat_val, prod_val in zip(uat_numeric, prod_numeric):
                        if pd.notna(uat_val) and pd.notna(prod_val):
                            # Subtract numbers if both are numeric
                            result.append(uat_val - prod_val)
                        else:
                            # Compare as strings if non-numeric
                            uat_str = str(df.loc[df.index[uat_val], col])
                            prod_str = str(df.loc[df.index[prod_val], prod_col])
                            result.append(f"Compare as strings: {uat_str} vs {prod_str}")
                    
                    comparison_results[comparison_key] = result

        comparison_df = pd.DataFrame(comparison_results)

        saveDfToCsvFile(comparison_df, fileNameOut, filePath)

    except Exception as e:
        print(f"An error occurred: {e}")
        raise RuntimeError("Failed to compare files.")
