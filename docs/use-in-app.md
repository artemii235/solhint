### Use Solhint in Your Application

If you want to use Solhint linter in your application - you may import `solhint/lib/index` file and run function 
*parseStr*.


```javascript
const linter = require('solhint/lib/index');


const report = linter.processStr(code, configAsJson);
report.messages.forEach(curError => console.log(curError.message));
```

### Solhint API

#### Functions
   
  **linter.parseStr**:
   
   - Arguments:
     - code {String} - Source code to validation
     - config {Object} - Object representation of .solhint.json configuration
   - Returns: 
     - report {Report} - object that contains list of errors and warnings
     
  **linter.parseFile**:
   
   - Arguments:
     - file {String} - Path to file for validation
     - config {Object} - Object representation of .solhint.json configuration
   - Returns: 
     - report {Report} - object that contains list of errors and warnings
    
  **linter.parsePath** 
  
   - Arguments:
     - path {String} - Glob path for validation
     - config {Object} - Object representation of .solhint.json configuration
   - Returns: 
     - report {Report} - object that contains list of errors and warnings
     
     
#### Objects

  **Report** 
  
   - *messages* {Message} - Message about error or warning
   - *filename* {String} - File name of validated source
   - *errorCount* {Number} - Count of error in current report
   - *warningCount* {Number} - Count of warnings in current report
   
  **Message**

   - *message* {String} - Error / warning message
   - *ruleId* {String} - Rule name
   - *severity* {Number} - Severity ID. Value of Report.SEVERITY.ERROR or Report.SEVERITY.WARN 
   - *column* {Number} - Column where error occurred
   - *line* {Number} - Line where error occurred
