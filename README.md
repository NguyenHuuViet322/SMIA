#  SMIA Project
<p align="center">
  <img src="img/aims_cover_image.png" />
</p>

## Getting Started

Welcome to the AIMS project. Here is a guideline to help you get started.

## Folder Structure

The workspace contains the following folders, where:

- `src`: the folder to maintain sources
- `lib`: the folder to maintain dependencies (JavafX and SQLite JDBC)
- `db`: the folder to maintain the database file
- `img\readme.jpg`: the folder to maintain the image resourse used in the project

## Dependency Management
### Working with Eclipse
Import the root directory of this repository after cloning under `Eclipse` -> `Open Projects from File System...` or by using EGit.

### Add VM arguments
Click on `Run` -> `Run Configurations...`  -> `Java Application`, create a new launch configuration for your project and add these VM arguments:
> --module-path lib/javafx-sdk-21.0.1/lib --add-modules javafx.controls,javafx.base,javafx.fxml,javafx.graphics,javafx.web

Keep in mind that the project is developed using JDK version 21. If you are using another version of it, kindly change it by double clicking into `JRE Library System` in the project directory in project explorer. 

##Refactoring

###FXML
- Before going into the coding, you should redesign the FXML file in the FXML package by modifying it using `Gluon SceneBuilder`. 
- I recommend that you need to:
	+ Change the whole color scheme of the program.
	+ Change the layout the scene.
	+ Change the name in the top left of the scene.
	+ Change the name of the FXML file. (You need to modify it on the code too or it'll cause some exception while running the app)
- <strong>Note: </strong> The element exist in the FXML file have `fx:id` that are used to identify them in code. If you want to modify them, make sure that the `fx:id` remain intact, or should you be creating another element with the same `fx:id`.

###Controller
- `ProductListController` : This is the controller for the Home of the App. You can refactor it to `HomeController`, `Index`, `ShopController`,...
- `ProductController`: This is the controller for the item appeared in the home window. You can refactor it to `ItemController`, `MediaController`,...
- `DBHandler`: This is the controller that is in charge of DBConnection and Query Executing. You can refactor it to `DatabaseController`, `SQLiteHandler`, `DbExecutor`,...
- `CartController`: This is the controller for cart window. You can refactor it to `ShoppingController`, `CartHandler`,...
- `CartItemController`: This is the controller for the item appeared in the cart window. You can refactor it to `CartItemHandler`, `ShoppingItemController`,...
- `InvoiceController`: This is the controller for the invoice details. You can refactor it to `BillController`, `DebitController`,...
- `PlaceOrderController`: This is the controller responsible for Placing order. You can refactor it to `OrderController`,...
- `ResultController`: This is the controller responsible for displaying the result of the transaction. You can refactor it to `TransactionResultController`, `OutcomeController`,...
- `RushOrderController`: This is the controller for the rush order form. You can refactor it to `FastOrderController`,...

- <strong>Note: </strong>You need to change the value of the `fx:controller` in the fxml file corresponding to the new name of the `Controller`.
- <strong>Note 2: </strong>You can shift the `VNPaySubsystemController` to the `Controller` package.
- <strong>Note 3: </strong> #djtmeNamGay.

###Model
- Remove all the `Card` model. (We are not fucking using them)
- I strongly recommend you to refactor as much as you can.

###Exception
- You can change the message of the `Exception`
- You can change the name of the `Exception`

###Adding product to the Shop
- Step 1: Add a product to `Product` table in the DB manually. (The ID value is auto-increment) <strong>You can use SQLite designer online or something equivalent</strong>
- Step 2: Add a image the `img` folder in the project with the name <<ID>>.jpg (example: 1.jpg) (I'm lazy so only jpg file, ok?)
