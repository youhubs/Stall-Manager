# Test Plan - D3

**Author**: Team58

## 1 Testing Strategy

### 1.1 Overall strategy

*The project will be tested at different levels: Unit Testing, Integration Testing, System Testing, and Regression Testing.*

- Unit testing will test the individual units or modules of the software, which will be performed by the QA lead and development lead. QA lead will produce the test cases and expected results.

- Integration testing will test multiple modules and their interactions, which will be performed by QA lead and development lead. QA lead will provide test cases and expected results.

- System testing will test the complete system as a whole. It includes both functional and non functional testings. Functional testing will be mostly based on the customer requirements and make sure that the system does what the customer wants it to do. Non functional testing will include performance tests, load tests, robustness tests, which will try to access the qualities of the system such as reliability, maintainability, and usability. System testing will be performed by QA lead and other team members.

- Regression testing is to make sure that changes to the codes will behave as intended and the unchanged codes are not negatively affected by the changes.  Regression testing will be performed by the QA lead and development lead. QA lead will produce the test cases and expected results.

### 1.2 Test Selection

*Black-box testing and white-box testing are two main families of testing techniques. Black-box testing is based on the description of the software while white-box testing is based on the code. We will choose suitable techniques for different testing levels.*

- For system/integration testing, we will focus on functional testing by using black-box testing techniques. Black-box testing will look at the description of the software and cover as much specified behavior in customer requirements as possible.

- The unit/integration level testing will be based on white-box  testing techniques. White-box testing will look at inside of the box which is based on the codes. It will cover as much coded behavior as possible.

- For regression testing, we will use both black-box testing and white-box testing techniques. The software behavior changes will be tested both through APP UI and JUnit testing cases.

### 1.3 Adequacy Criterion

*We will perform the testing at different levels to ensure that our software not only meets the functional requirements but also is strong enough to handle all kinds of exceptions or extreme situations.*

- At system/integration levels, we mainly focus on functional testing to check if our app meet the customer requirements, which will be performed mainly through UI. The systematic functional testing approach will be used. Specifically we will use Category-Partition Method to produce our test cases.

- At unit/regression testing levels, our testing will mainly focus on the codes to debug and enhance our codes. For example, statement coverage, branch coverage, condition coverage will be used for the unit testing. 

### 1.4 Bug Tracking

*A bug/enhance tracking system is used to track the reported bugs/enhancement during software development. It will record the life cycle of a bug: report time, report by, its severity, its behavior, its priority, fixed time, and fixed by. Similarly we can record the enhancement activity in this system. This system will provide us a clear overview of development requests and their states. For example, we can set up priority level of a bug as following.*

- Priority 1: highest, fix it immediately.

- Priority 2: urgent, fix it as soon as possible.

- Priority 3: not urgent, fix it if you have time.

### 1.5 Technology

*Tools that will be used in our testing:*

- JUnit: to perform the Unit testings.

- TSLGenerator: to produce the test cases by using category-partition technique for the system/integration testing.

## 2 Test Cases

<table style="width:100%">
  <tr>
    <th>Case #</th>
    <th>Purpose</th>		
    <th>Steps</th>
    <th>Expected Result</th>		
    <th>Actual Result</th>
  </tr>
  <tr>
    <td>01</td>
    <td>add or edit customer: one or more empty fields</td>
    <td>add or edit customer through UI</td>
    <td>alert message "Please Input All Fields!"</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>02</td>
    <td>add or edit customer: email without @</td>
    <td>add or edit customer through UI</td>
    <td>alert message "Please Input A Valid Email Address!"</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>03</td>
    <td>add or edit customer: email without dot</td>
    <td>add or edit customer through UI</td>
    <td>alert message "Please Input A Valid Email Address!"</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>04</td>
    <td>add or edit customer: everything is normal</td>
    <td>add or edit and view customer through UI</td>
    <td>customer is saved or updated</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>05</td>
    <td>view customer personal data</td>
    <td>display customer list through UI</td>
    <td>display customer firstName, lastName, zipcode, and email</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>06</td>
    <td>view customer purchase history</td>
    <td>select a customer and display his/her purchase history through UI</td>
    <td>display date, total purchase, payment information</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>07</td>
    <td>view customer rewards</td>
    <td>select a customrt and display reward summmary through UI</td>
    <td>display customer, reward balance, goldStatus, YTD Total</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>08</td>
    <td>purchase: amount empty or 0 or negative</td>
    <td>purchase through UI</td>
    <td>alert message "Please Input Purchase Amount First!"</td>
    <td>As Expected</td>
  </tr>
  <tr>
    <td>09</td>
    <td>purchase:amount&lt;$100;no reward;not goldStatus</td>
    <td>purchase through UI</td>
    <td>payment = amount; reward no change; goldStatus will be True if yearlySpending is more than 1000</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>10</td>
    <td>purchase:amount&lt;$100;apply reward;not goldStatus</td>
    <td>purchase through UI</td>
    <td>payment = amount-reward; reward reduces; goldStatus will be True if yearlySpending is more than 1000</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>11</td>
    <td>purchase:amount&lt;$100;no reward;applied goldStatus</td>
    <td>purchase through UI</td>
    <td>payment = amount*95%; reward no change; yearlySpending increases</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>12</td>
    <td>purchase:amount&lt;$100;apply reward;apply goldStatus</td>
    <td>purchase through UI</td>
    <td>payment = amount*95%-reward; reward reduces; yearlySpending increases</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>13</td>
    <td>purchase:amount>$100;no reward;not goldStatus</td>
    <td>purchase through UI</td>
    <td>payment = amount; reward+$10; goldStatus will be True if yearlySpending is more than 1000</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>14</td>
    <td>purchase:amount>$100;apply reward;not goldStatus</td>
    <td>purchase through UI</td>
    <td>payment = amount-reward; reward+$10 if payment>$100; goldStatus will be True if yearlySpending is more than 1000</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>15</td>
    <td>purchase:amount>$100;no reward;apply goldStatus</td>
    <td>purchase through UI</td>
    <td>payment = amount*95%; reward+$10 if payment>$100; yearlySpending increases</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>16</td>
    <td>purchase:amount>$100;apply reward;apply goldStatus</td>
    <td>purchase through UI</td>
    <td>payment = amount*95%-reward; reward+$10 if payment>$100; yearlySpending increases</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>17</td>
    <td>purchase:amount&lt;$10;apply reward;apply goldStatus</td>
    <td>purchase through UI</td>
    <td>payment=amount*95%-reward=0; reward reduces; yearlySpending no changes</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>18</td>
    <td>purchase:amount&lt;$10;apply reward;not apply goldStatus</td>
    <td>purchase through UI</td>
    <td>payment = 0; reward reduces; yearlySpending no changes</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>19</td>
    <td>send email: customer get $10 reward</td>
    <td>purchase through UI</td>
    <td>after a purchase and peyment>$100, alert message "Customer Eared $10. Email Send!"</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>20</td>
    <td>send email: customer reach goldStatus</td>
    <td>purchase through UI</td>
    <td>after a purchase and yearlySPending>$1000, alert message "Customer Achieves Gold Status. Email Sent!"</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>21</td>
    <td>delete customer</td>
    <td>select and delete a customer through UI</td>
    <td>deleted customer does not displayed in customer list</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>22</td>
    <td>add or edit customer: clear button</td>
    <td>clear customer information through UI</td>
    <td>click clear button should clear data in the fields</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>23</td>
    <td>test connection to database</td>
    <td>testCustomerHandler(): Right Click > Run As > Android JUnit Test</td>
    <td>database can be connected</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>24</td>
    <td>test method: saveCustomer()</td>
    <td>testSaveCustomer(): Right Click > Run As > Android JUnit Test</td>
    <td>saved customer data and can be verified by customer list</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>25</td>
    <td>test method: customerExists1()</td>
    <td>testCustomerExists(): Right Click > Run As > Android JUnit Test</td>
    <td>Customer exists</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>26</td>
    <td>test method: customerExists2()</td>
    <td>testCustomerExists(): Right Click > Run As > Android JUnit Test</td>
    <td>Customer does not exist</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>27</td>
    <td>test method: getCustomerList()</td>
    <td>testCustomerExists(): Right Click > Run As > Android JUnit Test</td>
    <td>List customer data in the LogCat</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>28</td>
    <td>test method: getCustomer()</td>
    <td>testCustomerExists(): Right Click > Run As > Android JUnit Test</td>
    <td>Customer information can be checked in LogCat</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>29</td>
    <td>test method: getCustomerId()</td>
    <td>testCustomerExists(): Right Click > Run As > Android JUnit Test</td>
    <td>get a customer and verified by its id</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>30</td>
    <td>test method: upateCustomer()</td>
    <td>testCustomerExists(): Right Click > Run As > Android JUnit Test</td>
    <td>Customer data is updated</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>31</td>
    <td>test method: deleteCustomer()</td>
    <td>testCustomerExists(): Right Click > Run As > Android JUnit Test</td>
    <td>Customer does not exist anymore</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>32</td>
    <td>test method: savePurchase()</td>
    <td>testCustomerExists(): Right Click > Run As > Android JUnit Test</td>
    <td>puchase is saved and can be verified by purchase list</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>33</td>
    <td>test method: getPurchaseList()</td>
    <td>testCustomerExists(): Right Click > Run As > Android JUnit Test</td>
    <td>get purchase list information in LogCat</td>
    <td>As expected</td>
  </tr>
  <tr>
    <td>34</td>
    <td>test method: getYTDSpending()</td>
    <td>testCustomerExists(): Right Click > Run As > Android JUnit Test</td>
    <td>this method comes up with the same result as the method customer.getYtdSpending(0 does</td>
    <td>As expected</td>
  </tr>
</table>
