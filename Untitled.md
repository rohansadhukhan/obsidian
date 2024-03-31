
```
ada credentials update --account=780833513986 --provider=conduit --role=IibsAdminAccess-DO-NOT-DELETE
```



```
curl --request POST \
--url http://127.0.0.1:80 \
--header 'content-encoding: amz-1.0' \
--header 'content-type: application/json; charset=UTF-8' \
--header 'x-amz-target: com.amazon.sheriffconfigurableruleexecutor.SheriffConfigurableRuleExecutor.DataSync' \
--data '{"__type": "com.amazon.sheriffconfigurableruleexecutor#DataSyncRequest","requestId":"Abcd1234-Ab12-Ab12-Ab12-Abcd1234efgh","teamId":"349ba95a-f6be-4e70-bbfb-b06a6f148b4e"}'
```

```
curl --request POST \
--url http://127.0.0.1:80 \
--header 'content-encoding: amz-1.0' \
--header 'content-type: application/json; charset=UTF-8' \
--header 'x-amz-target: com.amazon.sheriffconfigurableruleexecutor.SheriffConfigurableRuleExecutor.JsonRuleExecution' \
--data '{"__type": "com.amazon.sheriffconfigurableruleexecutor#JsonRuleExecutionRequest","requestId":"Abcd1234-Ab12-Ab12-Ab12-Abcd1234efgh","teamId":"349ba95a-f6be-4e70-bbfb-b06a6f148b4e","processId":"d82755d5-d509-4d8b-8fa6-8237f6a92127","rulesetName":"MyTimeValidations", "input": {"CHNWeekendOTHour":"22","EmployeeID":"1234", "PayDate": "20231128", "CostCenter": "nan"}}'
```


```
{
   "processId":"d82755d5-d509-4d8b-8fa6-8237f6a92127",
   "rulesetName":"MyTimeValidations",
   "datasetName":"MyTimeData",
   "rules":[
      {
         "ruleName":"ChinaHolidayOTHourRule",
         "conditions":[
            "CHNHolidayOTHour > 11"
         ],
         "outputData":{
            "Message":"Holiday OT Hour is greater than 11 hours"
         }
      },
      {
         "ruleName":"ChinaWeekendOTHourRule",
         "conditions":[
            "CHNWeekendOTHour > 11"
         ],
         "outputData":{
            "Message":"Weekend OT Hour is greater than 11 hours"
         }
      },
      {
         "ruleName":"ChinaTotalMonthlyOTHoursRule",
         "conditions":[
            "TotalMonthlyOT > 36"
         ],
         "outputData":{
            "Message":"Total monthly OT hours is greater than 36 hours"
         }
      },
      {
         "ruleName":"ChinaEmployeeHavingVTOandOTRule",
         "conditions":[
            "CHNVTOLessThanNYMFRNYMHour > 0",
            "CHNOTNYMONPTFVNYM > 0"
         ],
         "outputData":{
            "Message":"Employee having VTO and 1.5 OT"
         }
      },
      {
         "ruleName":"ChinaInternEmployeeHavingOtherPayCodeRule",
         "conditions":[
            "(CHNInternWorkingDay > 0 || CHNInternHolidayOTHour > 0)",
            "(CHNAbortionLeave > 0 || CHNMaternityPaidLeave > 0 || CHNNoReasonAbsence > 0 || CHNParentalLeave > 0 || CHNPaternityLeave > 0 || CHNPrePartumLeave > 0 || CHNVTOLessThanNYMFRNYMHour > 0 || CHNHolidayOTHour > 0 || CHNSwitchWeekendOTHour > 0 || CHNWeekendOTHour > 0 || CHNNSANYMONNYMUnit > 0 || CHNNSANYMTWNYMUnit > 0 || CHNProlongSickBaseNYMONZRZRNYM > 0 || CHNProlongSickBaseNYMNIZRNYM > 0 || CHNProlongSickBaseNYMEGZENYM > 0 || CHNProlongSickBaseNYMSVFVNYM > 0 || CHNProlongSickBaseNYMSVZRNYM > 0 || CHNProlongSickBaseNYMSXFVNYM > 0 || CHNProlongSickBaseNYMSXZRNYM > 0 || CHNProlongSickBaseNYMFVFVNYM > 0 || CHNProlongSickBaseNYMFVZRNYM > 0 || CHNProlongSickBaseNYMFRZRNYM > 0 || CHNProlongSickMinWageNYMEGZRNYM > 0 || CHNOtherUnpaidLeave > 0 || CHNRegularActualWorkingDay > 0 || CashOutCompanyAnnualLeaveBalance > 0 || CashoutStateAnnualLeaveBalance > 0 || CHNCashOutCOSTAL > 0 || CHNCashOutCOSUAL > 0 || CHNCashOutCYSTAL > 0 || CHNCashOutCYSUAL > 0 || CHNNoPayMaternityLeave > 0 || CHNOTNYMONPTFVNYM > 0 || CHNTOILPayout > 0)"
         ],
         "outputData":{
            "Message":"Intern having other pay codes"
         }
      },
      {
         "ruleName":"ChinaNegativeInternWorkingDaysRule",
         "conditions":[
            "CHNInternWorkingDay < 0"
         ],
         "outputData":{
            "Message":"Intern working day is less than"
         }
      }
   ],
   "identifier":[
      "PayDate",
      "CostCenter",
      "EmployeeID",
      "CHNAbortionLeave",
      "CHNMaternityPaidLeave",
      "CHNNoReasonAbsence",
      "CHNParentalLeave",
      "CHNPaternityLeave",
      "CHNPrePartumLeave",
      "CHNVTOLessThanNYMFRNYMHour",
      "CHNHolidayOTHour",
      "CHNSwitchWeekendOTHour",
      "CHNWeekendOTHour",
      "CHNNSANYMONNYMUnit",
      "CHNNSANYMTWNYMUnit",
      "CHNProlongSickBaseNYMONZRZRNYM",
      "CHNProlongSickBaseNYMNIZRNYM",
      "CHNProlongSickBaseNYMEGZENYM",
      "CHNProlongSickBaseNYMSVFVNYM",
      "CHNProlongSickBaseNYMSVZRNYM",
      "CHNProlongSickBaseNYMSXFVNYM",
      "CHNProlongSickBaseNYMSXZRNYM",
      "CHNProlongSickBaseNYMFVFVNYM",
      "CHNProlongSickBaseNYMFVZRNYM",
      "CHNProlongSickBaseNYMFRZRNYM",
      "CHNProlongSickMinWageNYMEGZRNYM",
      "CHNOtherUnpaidLeave",
      "CHNRegularActualWorkingDay",
      "CashOutCompanyAnnualLeaveBalance",
      "CashoutStateAnnualLeaveBalance",
      "CHNInternWorkingDay",
      "CHNInternHolidayOTHour",
      "CHNCashOutCOSTAL",
      "CHNCashOutCOSUAL",
      "CHNCashOutCYSTAL",
      "CHNCashOutCYSUAL",
      "CHNNoPayMaternityLeave",
      "CHNOTNYMONPTFVNYM",
      "CHNTOILPayout",
      "TotalMonthlyOT"
   ]
}
```




```
{
 "client_id": "SheriffPayrollLocker",
 "client_data_set_id": "CH_MyTime_Monthly",
 "pre_process_configs": {
  "executeApiProps": {
   "apiEndpoint": "gateway.gamma.locker.payroll.amazon.dev",
   "apiPath": "/files/download",
   "apiRegion": "us-west-2",
   "apiRoleArn": "arn:aws:iam::129938306172:role/Sheriff-client-role-for-payroll-locker"
  }
 },
 "response_configs": {
  "executeApiProps": {
   "apiEndpoint": "gateway.gamma.locker.payroll.amazon.dev",
   "apiPath": "/orchestration/clientcallback",
   "apiRegion": "us-west-2",
   "apiRoleArn": "arn:aws:iam::129938306172:role/Sheriff-client-role-for-payroll-locker"
  }
 },
 "sheriff_data_set_id": "CH_My Time_Monthly_Aggregated",
 "sheriff_data_set_info": {
  "country": "CHINA",
  "dataType": "CH_My Time_Monthly_Aggregated",
  "frequency": "Monthly"
 },
 "sheriff_data_set_type": "ANOMALY_INSIGHTS"
}
```

