
# ClickItApp

This software replicates user engagements with particular products on Bol.com, enabling a comprehensive assessment of the product's performance based on user interactions.

## Getting Started


This software is designed to run on a desktop system meeting the following requirements:

- A UI-based operating system (MacOS, Linux, Windows)
- Web browser drivers are either installed or can be easily installed.
- A shell terminal or equivalent, such as bash

Needed packages are:

- node.js
- i18n-iso-countries [optional]
- selenium-webdriver
- web browsers drivers as you see fit

    The application is using Safari, Chrome and Firefox at the moment.

- For list of packages view [package.json](package.json)


## Installation

To set up the program, follow these steps:

1. Download the package to your preferred directory.
1. Install Node.js on your system.
1. Install Selenium.
1. Install the web browser drivers of your choice. Note that, in most cases, browser drivers are automatically installed with Selenium.
1. Copy the [links-sample.json](links-sample.json) to `links.json`. Subsequently, update it with the relevant text (ensure no comments are left in the file).
    ```
    {
    "groups": [
        {
            "name": "ProductName1",
            "products": [
                {
                    "searchStr": "",
                    "searchTerm": "",
                    "productTitle": "",
                    "repeatCount": 1,
                    "fluctuation": 10,
                    "minWait": 2,
                    "maxWait": 5
                }
            ]
        }
    }
    ```

    - **name**: Give each product group a name. This could be used when an app is going to be used for couple of the product groups instead of all.
        - *Note*: Name must be unique. 

    - **products**: Arrange products into groups for simultaneous execution.
        - *Note*: Limit each group to a maximum of three products.

        - **searchStr**: Specify the string to be used in the search field on the site.

        - **searchTerm**: Define the string that the search autocomplete will suggest.

        - **productTitle**: Provide the complete product title that you want to be clicked.

        - **repeatCount**: [Optional] Indicate the number of times you want the product to be clicked. Default is 10.
            - *Note*: A random number between 0 and *fluctuation* will be added to this number to enhance the app's detection evasion.


        - **fluctuation**: [Optional] Indicates the maximun number that can be randomly add to the repeatCount. Default is 10.
    
        - **minWait**: [Optional] Set the minimum wait time in seconds before initiating the next click. The default is 2 seconds.

        - **maxWait**: [Optional] Set the maximum wait time in seconds before initiating the next click. The default is 5 seconds.

1. Open the command prompt (cmd) to execute the application.

If you encounter any issues or have further questions during the installation process, feel free to ask for assistance or [create an issue](https://github.com/RahamRaf/ClickItApp/issues/new).

## Usage

**Primary Application Interface**

You can utilize the application's user interface (UI) to initiate the clicking process when it is accessible. However, the primary method of using the app at this time is through the command prompt (cmd). The application's user interface is currently in development and may be released in the near future.

  ```
  cd /path/to/the/app/directory/

  node main.js
  ```
  or
  ```
  node main.js [GroupOfProduct1] [GroupOdProduct2] [...]
  ```

  If **_GroupOfProducts_** are added, the app will run for those group of products only. Otherwise, the app will process all products.

**Execute for Single Link**

The application can be configured to operate for a single link, utilizing the command prompt (cmd) rather than the links.json file. However, please note that this functionality is primarily intended for testing purposes.

  ```
  cd /path/to/the/app/directory/

  node inc/clickOneLink.js \
      'search phrase' \
      'Full search term autocompleted by the website' \
      'Full Product Title' \
      [repeatCount] \
      [fluctuation] \
      [MinWaitTimeOnProducPage] \
      [MaxWaitTimeOnProducPage]
  ```

*__Note__*: These arguments are optional:

- **repeatCount** default is 10
- **fluctuation** default is 10
- **MinWaitTimeOnProducPage** default is 2sec
- **MaxWaitTimeOnProducPage** default is 5sec

*__Example__*:
```
node main.js bido 'bidon' "All Together Drinkfles - Opvouwbare Bidon - Opvouwbare Waterfles - 500ml - Silicone - Donkergrijs" 20 
```

## Contributing

Thank you for considering contributing to this project! Contributions are welcome and encouraged.

### How to Contribute

1. Fork the repository.
1. Clone the forked repository to your local machine.
1. Create a new branch for your changes.
  ```
  git checkout -b feature/your-feature
  ```
4. Make your changes and commit them.
  ```
  git add .
  git commit -m "Add your meaningful commit message"
  ```  
5. Push your changes to your forked repository.
  ```
  git push origin feature/your-feature
  ```  
6. Create a pull request (PR) to the main branch of the original repository.

### Reporting Issues

If you encounter issues or have suggestions for improvements, please open an issue on the [Issues page](https://github.com/RahamRaf/ClickItApp/issues).

## Authors

This is a project by [JAssist](https://jassist.eu) by [JoopeA](https://joopea.info).

Main contributor:

* [Raham Rafiee](raham@joopea.com)

## License

This program is developed for All Together (Amasterdam registered company).

This project is licensed under the Copyright © 2023 JoopeA™ Foundation. All rights reserved.

