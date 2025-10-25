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

Start-Sleep - seconds 1.5

#find elements

$MachineElements = $driver..FindElementByXpath("//find html by xpath")
$ModelElements = $driver..FindElementByXpath("//find html by xpath")
$RoleElements = $driver..FindElementByXpath("//find html by xpath")
$LanguageElemetns = $driver..FindElementByXpath("//find html by xpath")
$MACElements = $driver..FindElementByXpath("//find html by xpath")

#to replace the MAC address without colon
$Nocolon = $MACElements.Text -replace ":","" 

$SerailElements = $driver..FindElementByXpath("//find html by xpath")
$AssetElements = $driver..FindElementByXpath("//find html by xpath")

#to convert the extracted data to text
$fields = @{
  "MachineName" = $MachineElements.Text
  "ModelName" = $ModelElements.Text
  "Role" = $RoleElements.Text
  "Language" = $LanguageElemetns.Text
  "MACName" = $Nocolon
  "SerialName = $SerailElements.Text
  "AssetName" = $AssetElements
  "MAC" = $MACElements.Text
  }

$field.Values | Outfile -FilePath "C:\Script\Input\Out.txt"

$driver.Quit()

#webdriver for edge
$driverPath = "C:\Scripts\Input"

#Create a Webdriver instance
$driver = New-Object OpenQA.selenium.Edge.EdgeDriver($driverPath)

#navigate to Webpage
$driver.Navigate().GoToUrl("http://your webpage")


