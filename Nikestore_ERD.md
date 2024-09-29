# Nike Store ERD 

```mermaid

erDiagram

 PRODUCT {
    int product_id PK
    string model_name
    float price 

 }
 
 CUSTOMER {
    int customer_id PK
    string name 
    string email 
    string phone_number
 }
 SALE {
    int sale_id PK 
    int customer_id FK
    int product_id FK 
    date sale_date
    int quantity 

 }
 INVENTORY {
    int product_id FK 
    int quantity
    string wearhouse_location
 }

PRODUCT ||--o{ SALE : "purchased in"
CUSTOMER ||--O{ SALE : "makes"
PRODUCT ||--o{ INVENTORY : "stored in"
