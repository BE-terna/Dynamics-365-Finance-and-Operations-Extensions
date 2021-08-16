This section, summarizes additional General Ledger features, which are part of the LOC_LEDGER extended localization package.

-----

# Journalize tax as the parent line

This extended localization functionality enables posting tax to the same offset account as the line from which the tax is derived. Journalizing tax as a parent line is available only if posting definitions are enabled. If the “Journalize tax as parent line” option is enabled, tax is always posted with the same offset account as the original line from which the tax is derived.

[Detailed documentation](/Help/Extended-Localization/General-Ledger-features/Journalize-tax-as-parent-line)

-----

# Year-end procedure enhancements

The functionality enables balancing the Main account balance with Ledger account balance in order to avoid opening transactions in cases where Ledger account balance equals zero and the Main account balance does not. The feature is useful if at the end of the year a different balance on each main account - financial dimension combination s remains, while balance for the same main account (combining all the dimensions) is zero.

This extended localization feature enables a proposition for balancing General Ledger transactions from the General journal. As a result, journal lines with settlement proposals are generated. After the journal is posted, balance on both, Ledger account and Main account, is zero.

[Detailed documentation](/Help/Extended-Localization/General-Ledger-features/Year-end-procedure-enhancements)