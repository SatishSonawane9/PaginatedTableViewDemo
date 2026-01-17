# PaginatedTableViewDemo
iOS Products App – Paginated TableView with Networking
 Overview
This iOS application displays a list of electronic products fetched from a paginated API. It is built using UIKit, follows MVVM architecture, and demonstrates clean separation of concerns, pagination, networking, and error handling.

 Features
	•	API Integration using URLSession
	•	Pagination support (loads more data on scroll)
	•	UITableView with Custom Cells
	•	Product Detail Screen
	•	Loading Indicator (Footer Spinner)
	•	Graceful Error Handling
	•	Codable-based JSON Parsing
	•	Lazy Image Loading
	•	MVVM Architecture

 Tech Stack
	•	Language: Swift
	•	UI Framework: UIKit (Storyboard-based)
	•	Architecture: MVVM
	•	Networking: URLSession
	•	Parsing: Codable
	•	Minimum iOS Version: iOS 13+

 API Details
Endpoint

https://fakeapi.net/products?page=0&limit=10&category=electronics
Response Structure

{
  "data": [Product],
  "pagination": {
    "page": 1,
    "limit": 10,
    "total": 20
  }
}
Pagination is handled using the page value from the response.

Architecture
MVVM Breakdown
Model
	•	Product
	•	ProductResponse
	•	Pagination
View
	•	ProductListViewController
	•	ProductDetailViewController
	•	ProductCell
ViewModel
	•	ProductListViewModel
	◦	Handles API calls
	◦	Manages pagination
	◦	Exposes callbacks for UI updates
Service Layer
	•	APIServiceProtocol
	•	APIService

Pagination Flow
	1	Initial API call loads page 0
	2	When last cell appears:
	◦	loadMoreIfNeeded(index:) is triggered
	3	Next page is fetched using response pagination
	4	New products are appended to the list

Loading State
	•	Footer spinner (UIActivityIndicatorView) shown while fetching data
	•	Prevents duplicate API calls using isFetching flag

Error Handling
	•	Handles:
	◦	No Internet
	◦	Invalid response
	◦	Decoding failures
	•	Displays error state with retry option

Screens
Product List Screen
	•	Displays:
	◦	Image
	◦	Title
	◦	Description
	◦	Category
	◦	Price
Product Detail Screen
	•	Shows full product information
	•	Loaded via navigation push

How to Run
	1	Clone the repository
	2	Open .xcodeproj in Xcode
	3	Run on Simulator or Device
	4	Ensure internet connection is available
	
 Author
Satish S iOS Developer

📌 Notes
This project was created as part of an iOS assignment to demonstrate:
	•	UIKit proficiency
	•	Networking & pagination
	•	Clean architecture
	•	Production-ready coding practices
