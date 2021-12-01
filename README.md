# daclifymodules
Module contracts to attach to the daclify core contract

## payroll
first deploy payroll smart contract to a new account
then run action on the main dac group contract called "linkmodule"

### example:
"has_contract": true, 
"module_name": "payroll", //always this name as it's configured on the UI
"slave_permission": {"actor": "bludacpayrol", "permission": "owner"}

then run action on the payroll smart contract called "freeze"
set freeze: false //this will unfreeze the payroll module

next step is to run "payrollreg" action to register new payroll in the payroll module
