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


example transaction:
```
cleos -u https://wax.greymass.com push transaction '{
  "delay_sec": 0,
  "max_cpu_usage_ms": 0,
  "actions": [
    {
      "account": "bludacpayrol",
      "name": "payrollreg",
      "data": {
        "payroll_tag": "blupay",
        "pay_from": "bludacpayrol",
        "xfer_permission": "active",
        "payment_token": {
          "contract": "eosio.token",
          "quantity": "0.00000000 WAX"
        },
        "description": "BluPayroll"
      },
      "authorization": [
        {
          "actor": "thebludacdao",
          "permission": "owner"
        }
      ]
    }
  ]
}'
```
