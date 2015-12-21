# Vision Document

**Author**: Team 58

## 1 Introduction

Payment and Rewards Management System (PReMS) is an android based application that will allow for the management and tracking of loyal customer's purchases and rewards.  It is intended to be used by a mobile shop manager.

## 2 Business Needs/Requirements

There currently is not a good mobile point of sale (PoS) solution that will allow for a mobile shop manager process payments, track a customer's purchases, and allow for any type of rewards program.

Mobile shop managers will benefit from a solution that is as mobile as their buisness.  Creating an application on the android platform will allow for a shop manager to process credit card transactions as well as track purchases.  The ability to track purchases will allow for the shop manager to implement a rewards program for their most loyal customers.

## 3 Product / Solution Overview

PReMS will be an android based application that will process payments, store purchase information and track rewards information.  This system will also e-mail customers when they have earned a reward in the rewards program.

## 4 Major Features

######Home Screen
*This is the first screen that the mobile manager will see.  It will allow for the manager to add a new customer, or view an existing customer.*
- Add Button
	- Advance to the Customer Add/Edit Screen with the add option
- View Button
	- Advance to the view customer screen

######Customer Add/Edit Screen
*This screen will allow the system to gather information on a customer and add them to the system* 
- First Name Field
	- Text based field that will allow for the customers first name to be entered.
- Last Name Field
	- Text based field that will allow for the customers last name to be entered.
- Zipcode Field
	- Numeric based field that will allow for the customers zipcode to be entered.
- E-Mail Field
	- Text based field that will allow for the customers e-mail address to be entered.   
- Add Button
	- Accept the values that have been input into the fields and add it to the customer base. 
    **This button is only visible with add option*
- Update Button
	- Update user information.
	**This button is only visible with the update option*
- Clear Button
	- Clears all of the fields on the interface
- Back Button
	- Returns to the View Customer Screen (Edit Option)
	- Returns to the Home Screen (Add Option)


######View Customer Screen
*This screen will allow for the manager to look up information about individual customers.*
- Customer List
	- This will present a list of all customers currently in the system and allow for the selection of a single customer
- Add Purchase Button
	- Advance to the Add Transaction Screen
- View Purchase List Button
	- Advance to the Transaction List Screen
- View Rewards Button 
	- Advance to the Rewards Status Screen
- Edit Customer Button
	- Advance to the Customer Add/Edit Screen with the edit option
- Delete Customer Button
	- Removes the customer from the system.
- Back Button
	- Return to the Home Screen

######Add Purchase Screen
*This screen will process the payments and add the purchase to the system.*
- Customer Display
	- This will display the information for the currently selected customer.
- Purchase Total Field
	- Floating point field that will accept the total amount of the purchase.
- Purchase Total Display
	- Shows the total of the purchase before discounts are applied.
- Gold Discount Display
	- Shows the amount discounted due to gold rewards. 
- Rewards Amount Display
	- Shows the amount discounted due to accumulated rewards.
- Checkout Button
	- Add the purchase to the system
- Back Button
	- Return to the View Customer Screen

######View Purchases Screen
*This screen will display the purchases that a customer has made*
- Customer Display
	- This will display the information for the currently selected customer.
- Transaction Table
	- This table will display the purchase date, amount and rewards applied.
- Back Button
	- Return to the View Customer Screen

######View Rewards Status Screen
*This screen will display the the progress toward gold status as well as the rewards balance*
- Year To Date Total Spent Field
	- This will display the total amount that has been spent this year
- More To Spend Field
	- Display the amount that the customer still has to spend to acheive gold status
- Reward Balance Field
	- The customer's reward balance.
- Gold Member Boolean
	- Shows if the customer is a gold member.
- Back Button
	- Return to the View Customer Screen

## 5 Scope and Limitations

The initial release will only allow for a single stall manager to manage a single stall.  The rewards program will be limited to two rewards plans.  Gold Status and $100 reward.