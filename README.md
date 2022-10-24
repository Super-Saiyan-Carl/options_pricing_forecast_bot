# OPTIONS PRICING FORECAST BOT
## Group Project 2 for DU Fintech Bootcamp

## Objective: To qualify the user with a few questions in an Amazon Lex Bot, and apply machine learning to suggest potential options contracts for their preferred stock.

### AMAZON LEX BOT (utilizing AWS):

<img width="399" alt="Screen Shot 2022-10-20 at 3 27 41 PM" src="https://user-images.githubusercontent.com/108194033/197062222-ac16f258-25b1-426f-9335-920cd61a45fe.png"> <img width="397" alt="Screen Shot 2022-10-20 at 3 28 03 PM" src="https://user-images.githubusercontent.com/108194033/197062226-e12b6d96-6970-482f-a81c-ce85996cd006.png">

Supports Python 3.7+

Libraries Imported:

<img width="507" alt="Screen Shot 2022-10-20 at 3 31 43 PM" src="https://user-images.githubusercontent.com/108194033/197062952-0cbcbf6c-dd0d-483b-b031-2341d32fc6b3.png">

By using the Polygon API and the `load_dotenv()` function, we retrieve a financial report of a particular stock.

Source: [Polygon API & Documentation](<https://polygon.io/docs/options/getting-started>)

`POLYGON_API_KEY = os.getenv("POLYGON_API_KEY")`

`client = RESTClient(POLYGON_API_KEY)`

By using the Alpaca API, we retrieve closing price data of a particular stock.

Source: [Alpaca](<https://alpaca.markets/>)

`alpaca_api_key = os.getenv("ALPACA_API_KEY")`

`alpaca_api_secret_key = os.getenv("ALPACA_API_SECRET_KEY")`

After creating a DataFrame and cleaning it up, we begin our machine learning models.

SIMPLE MOVING AVERAGES (SMA):

Using short, medium, long, and super long timeframes, we begin to build our SMA strategy return vs actual returns.

<img width="834" alt="Screen Shot 2022-10-20 at 4 48 44 PM" src="https://user-images.githubusercontent.com/108194033/197073588-471c350a-cbdf-4efb-bb78-291ba4706e91.png">

INTIALIZE AND SET BUY/SELL SIGNALS:

<img width="632" alt="Screen Shot 2022-10-23 at 11 18 43 PM" src="https://user-images.githubusercontent.com/108194033/197453448-64c011f8-1421-4b79-9da7-38e8d762b5d2.png">

EXAMPLE OF OUR DAILY AND ANNUAL RETURNS DATAFRAME:

<img width="778" alt="Screen Shot 2022-10-23 at 11 22 47 PM" src="https://user-images.githubusercontent.com/108194033/197453838-3d5a609e-e338-42f9-88bf-43466ddb0e53.png">

HVPLOT SHOWCASING ALL MOVING AVERAGE WINDOWS AGAINST ACTUAL RETURNS:

<img width="755" alt="Screen Shot 2022-10-20 at 7 48 00 PM" src="https://user-images.githubusercontent.com/108194033/197455609-05ca329c-5e81-4c4a-a415-209817896d2e.png">

Next, the data is scaled, trained, and fit using ```StandardScaler``` and modeled through ```LogisticRegression``` where we can predict our returns. A classification report is generated, and using ```hvplot```, the predicted returns vs actual returns chart shows a model that is 50/50 just okay, with further analysis needed to understand the extreme deviation at the end of the chart.

<img width="428" alt="Screen Shot 2022-10-23 at 11 36 45 PM" src="https://user-images.githubusercontent.com/108194033/197455439-c82c4e0f-e773-42e5-8bb0-6da1067c2a63.png">

<img width="380" alt="Screen Shot 2022-10-23 at 11 36 57 PM" src="https://user-images.githubusercontent.com/108194033/197455462-17f2edec-cf08-4d9d-bea6-4dda2524520a.png">

## Contributors:
Tanner Franklin, Tyler Hillison, Carl Mikel, Drew Pagnotta
