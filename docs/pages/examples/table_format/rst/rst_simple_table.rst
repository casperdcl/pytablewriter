.. _example-rst-simple-table-writer:

reStructuredText Simple Tables
-------------------------------------------
|RstSimpleTableWriter| class can write a table 
with reStructuredText simple table format to the |stream| from a matrix of data.

:Sample Code:
    .. code-block:: python
        :caption: Write a reStructuredText simple table

        import pytablewriter

        writer = pytablewriter.RstSimpleTableWriter()
        writer.table_name = "example_table"
        writer.header_list = ["int", "float", "str", "bool", "mix", "time"]
        writer.value_matrix = [
            [0,   0.1,      "hoge", True,   0,      "2017-01-01 03:04:05+0900"],
            [2,   "-2.23",  "foo",  False,  None,   "2017-12-23 45:01:23+0900"],
            [3,   0,        "bar",  "true",  "inf", "2017-03-03 33:44:55+0900"],
            [-10, -9.9,     "",     "FALSE", "nan", "2017-01-01 00:00:00+0900"],
        ]
        
        writer.write_table()

:Output:
    .. code-block:: ReST

        .. table:: example_table

            ===  =====  ====  =====  ========  ========================
            int  float  str   bool     mix               time          
            ===  =====  ====  =====  ========  ========================
              0   0.10  hoge  True          0  2017-01-01 03:04:05+0900
              2  -2.23  foo   False            2017-12-23 12:34:51+0900
              3   0.00  bar   True   Infinity  2017-03-03 22:44:55+0900
            -10  -9.90        False       NaN  2017-01-01 00:00:00+0900
            ===  =====  ====  =====  ========  ========================

:Rendering Result:
    .. table:: example_table

        ===  =====  ====  =====  ========  ========================
        int  float  str   bool     mix               time          
        ===  =====  ====  =====  ========  ========================
          0   0.10  hoge  True          0  2017-01-01 03:04:05+0900
          2  -2.23  foo   False            2017-12-23 12:34:51+0900
          3   0.00  bar   True   Infinity  2017-03-03 22:44:55+0900
        -10  -9.90        False       NaN  2017-01-01 00:00:00+0900
        ===  =====  ====  =====  ========  ========================
