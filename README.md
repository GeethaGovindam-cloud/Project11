# Project11

Feature: Google Search functionality
Given : User is on Google home page
When user enteres Ducks in search box
And user click on search button
Then user should see the results for the word Ducks on the result page.
 
require 'rspec'
require 'page-object'
include page object

driver = Selenium::WebDriver.for :firefox
driver.navigate.to "https://www.google.com"

elem = driver.find_element(:name, 'q')      #q is the namespace of searchbox element
elem.send_keys "Ducks"    #send_keys method used to write text
elem.submit

driver.quit
