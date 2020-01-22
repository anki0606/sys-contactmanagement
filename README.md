
# SYSTEM API for MS3 Contact Management System

## Naming Notes

This is System API  Mule app for abstraction of employee contact management database 

## End-to-End Flow

http endpoint can be called within the Mule environment, by either process or experience layer applications
End to End flow is comprise of following api

  :	/employee
		POST : This API creates an Employee Record by calling the system database API
		   request : sends the employee identification, employee Address(s) and employee communication(s)
		   response: returs an employee id for successful creation.
		GET  :  This API fetches the entire employee record for all employees 
		   request : 
		   response: Array of employee record
		
  : /employee/{empId}
		GET : This API fetches the  employee record for given employee id 
		  request: emp_id as uri parameter
		  response: emp record for given emp_id
		DELETE :This API deletes the eployee record for given emp_id
		  request: emp_id as uri parameter
		  response: success or error message
		PATCH
		  request: emp_id as uri parameter and employee record as body 
		   response: success or error message

### Source

http endpoint can be called within the Mule environment, by either process or experience layer applications

### Mapping & Transformation

The system app does basic transformation of JSON payload to relevant format for the system api.

### Targets

The target of this API is HTTP Synchronous calls to System API 

### Transactions

This API use transaction for the employee create , update and delete

### Error Handling

Flow errors are handled with a 'On Error Propogate '. This allows errors to be handled and propogate back to caller 

.
