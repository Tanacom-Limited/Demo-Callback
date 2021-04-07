# Demo Callback function


A Callback function is a function that is passed as an argument to another function, to be “called back” at a later time. Also know as "Call- After" function and is invoked after the first function completes.

Below is a sample code written in Javascript.

WITHOUT CALLBACK
================

````


var companies = ["Tanacom Limited","TLM Limited","Samospharma Limited"];

// Add A Company Function.
function addCompany(company) {
    setTimeout(() => {
        companies.push(company)
    }, 150);
}

// Get All Companies Function.
function getCompanies() {
    setTimeout(() => {
        console.log(companies);
    }, 50);
    
}

//Calling our Functions

addCompany("Graidup Limited");

getCompanies();

/** getCompanies function is call first due to the timeout
* instead of the addCompany. We are using the setTimout to indicate 
*delay with our database server in real case.
* 
*/

// OUTPUT :['Tanacom Limited', 'TLM Limited', 'Samospharma Limited']

````



WITH CALLBACK
================

The above issue can be solved by using Callback.


````


var companies = ["Tanacom Limited","TLM Limited","Samospharma Limited"];

// Add A Company Function.
function addCompany(company,ourCallback) {
    setTimeout(() => {
        companies.push(company)
        ourCallback()
    }, 150);
}

// Get All Companies Function.
function getCompanies() {
    setTimeout(() => {
        console.log(companies);
    }, 50);
    
}

//Calling our Functions

addCompany("Graidup Limited",getCompanies);


// OUTPUT :['Tanacom Limited', 'TLM Limited', 'Samospharma Limited', 'Graidup Limited']
// getCompanies invoke after addCompany has finish executing.


````
