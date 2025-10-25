# Webpage-Data
Powershell selenium with Edge Webdriver to extract data
Import-Module Selenium

#webdriver for Edge
$driverPath = "C:\Scripts\input"

#create Webdriver instance
$driver = New-Objeect OpenQA.selenium.Edge.EdgeDriver($driverPath)

#start measuring time
$stopwatch = Measure-Command {

#navigate to Webpage
$driver.Navigate().GoToUrl("http://your webpage")

$driver.manage().Window.Maximize()

$driver.FindElementByXpath("//find html by xpath").sendkeys("Assetnumber")

$driver.FindElementByXpath("//find html by xpath").Click()

