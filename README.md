```mermaid
erDiagram
    User ||--o{ Alarm : has
    User ||--o{ Inquiry : makes
    User ||--o{ Order : places
    User ||--o{ Reply : makes
    User ||--o{ Review : writes
    User ||--o{ SalesLog : generates
    User ||--|| Store : owns
    User ||--|| Cart : has
    User }o--|{ FavoriteStore : favorites
    User }|--|| Grade : belongs to

    Grade ||--o{ User : has

    Store ||--o{ Product : sells
    Store ||--o{ SalesLog : generates
    Store }o--|{ FavoriteStore : favorited by
    Store ||--o{ DailyStoreSales : has
    Store ||--o{ WeeklyStoreSales : has
    Store ||--o{ MonthlyStoreSales : has
    Store ||--o{ yearlyStoreSales : has

    FavoriteStore }|--|| User : favorited by
    FavoriteStore }|--|| Store : favorites

    Product }|--|| Store : belongs to
    Product }|--|| Category : belongs to
    Product ||--o{ Review : has
    Product ||--o{ Inquiry : has
    Product ||--o{ Stock : has
    Product ||--o{ CartItem : included in
    Product ||--o{ OrderItem : included in
    Product ||--o{ SalesLog : generates

    Category ||--o{ Product : has

    Stock }|--|| Product : belongs to
    Stock }|--|| Size : has

    Size ||--o{ Stock : has
    Size ||--o{ CartItem : has
    Size ||--o{ OrderItem : has

    Inquiry }|--|| User : made by
    Inquiry }|--|| Product : about
    Inquiry ||--|| Reply : has

    Reply }|--|| Inquiry : answers
    Reply }o--|| User : made by

    Review }|--|| User : written by
    Review }|--|| Product : about
    Review }|--|| OrderItem : linked to

    Cart ||--o{ CartItem : contains
    Cart }|--|| User : belongs to

    CartItem }|--|| Cart : belongs to
    CartItem }|--|| Product : is a
    CartItem }|--|| Size : has

    Order }|--|| User : placed by
    Order ||--o{ OrderItem : contains

    OrderItem }|--|| Order : belongs to
    OrderItem }|--|| Product : is a
    OrderItem }|--|| Size : has
    OrderItem ||--|| Review : has

    SalesLog }|--|| User : by
    SalesLog }|--|| Store : from
    SalesLog }|--|| Product : for

    DailyStoreSales }|--|| Store : belongs to
    WeeklyStoreSales }|--|| Store : belongs to
    MonthlyStoreSales }|--|| Store : belongs to
    yearlyStoreSales }|--|| Store : belongs to

    Alarm }|--|| User : belongs to
```
