An error occurred: numpy boolean subtract, the `-` operator, is not supported, use the bitwise_xor, the `^` operator, or the logical_xor function instead.
Traceback (most recent call last):
  File "D:\Users\jvictor\OneDrive - LayerOne\Documents\Work\General Use\repos\P1RestAPI\src\Positions\Helpers.py", line 73, in clean_and_compare
    result.append(uat_val - prod_val)
                  ~~~~~~~~^~~~~~~~~~
TypeError: numpy boolean subtract, the `-` operator, is not supported, use the bitwise_xor, the `^` operator, or the logical_xor function instead.

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "D:\Users\jvictor\OneDrive - LayerOne\Documents\Work\General Use\repos\P1RestAPI\src\main.py", line 90, in <module>
    main()
  File "D:\Users\jvictor\OneDrive - LayerOne\Documents\Work\General Use\repos\P1RestAPI\src\main.py", line 66, in main
    clean_and_compare(df=mergedDf, uat_suffix="_uat", prod_suffix="_prod", dfFileName=f"diffs_{view_name}_{start_date}_{end_date}.csv", filePath=pathDiff)
  File "D:\Users\jvictor\OneDrive - LayerOne\Documents\Work\General Use\repos\P1RestAPI\src\Positions\Helpers.py", line 88, in clean_and_compare
    raise RuntimeError("Failed to compare files.")
RuntimeError: Failed to compare files.
