An error occurred: only integers, slices (`:`), ellipsis (`...`), numpy.newaxis (`None`) and integer or boolean arrays are valid indices
Traceback (most recent call last):
  File "D:\Users\jvictor\OneDrive - LayerOne\Documents\Work\General Use\repos\P1RestAPI\src\Positions\Helpers.py", line 73, in clean_and_compare
    uat_str = str(df.loc[df.index[uat_val], col])
                         ~~~~~~~~^^^^^^^^^
  File "D:\Users\jvictor\.pyenv\pyenv-win\versions\3.12.0\Lib\site-packages\pandas\core\indexes\range.py", line 1024, in __getitem__
    raise IndexError(
IndexError: only integers, slices (`:`), ellipsis (`...`), numpy.newaxis (`None`) and integer or boolean arrays are valid indices

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "D:\Users\jvictor\OneDrive - LayerOne\Documents\Work\General Use\repos\P1RestAPI\src\main.py", line 90, in <module>
    main()
  File "D:\Users\jvictor\OneDrive - LayerOne\Documents\Work\General Use\repos\P1RestAPI\src\main.py", line 66, in main
    clean_and_compare(df=mergedDf, uat_suffix="_uat", prod_suffix="_prod", dfFileName=f"diffs_{view_name}_{start_date}_{end_date}.csv", filePath=pathDiff)
  File "D:\Users\jvictor\OneDrive - LayerOne\Documents\Work\General Use\repos\P1RestAPI\src\Positions\Helpers.py", line 85, in clean_and_compare
    raise RuntimeError("Failed to compare files.")
RuntimeError: Failed to compare files.
