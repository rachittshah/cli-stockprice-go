## About

This Go script is a web scraper that uses the Colly library to scrape historic stock data from Yahoo Finance and plot it using the Asciigraph library. The script takes a stock symbol as a command-line argument, with "MSFT" as the default symbol.

In the main function, the script starts a timer and sets up a command-line flag for the stock symbol. It then calls the getHistoricData() function, passing in the stock symbol from the command-line flag. After the getHistoricData() function completes, the script prints the time it took to run the code.

The getHistoricData() function creates a new Colly collector and sets some options for the collector, including the user agent, allowed domains, and parallelism limit. The function also sets up callbacks for when a request is made and when the HTML body is received.

The callback for when the HTML body is received, the script parses the data from the table and stores it in a slice, reversing the order of the slice. Then it calls the asciigraph.Plot() function to plot the data in the slice and print the graph in the console.

Finally, the function visits the Yahoo Finance page for the specific stock symbol passed in and wait for all the requests to complete.

## Installation

To install and use this script, you will need to have Go installed on your system. You can check if Go is installed by running ```go version``` in your command line. If Go is not installed, you can download and install it from the official [Go website](https://golang.org/dl/).

Once you have Go installed, you can install the necessary dependencies by running the following command:
```
go get -u github.com/gocolly/colly github.com/guptarohit/asciigraph
```

This command installs the Colly and Asciigraph library which the script depends on.

To run the script, you can use the following command :
```
go run main.go -stock="STOCK_SYMBOL"
```

replace STOCK_SYMBOL with the stock symbol you want to scrape data for.

The script will then scrape historic stock data from Yahoo Finance for the specified stock symbol and plot it using the Asciigraph library.

You can also build the script using
```
go build main.go
```

This will create an executable file of the script in your current directory. you can use this executable to run the script on your system.
