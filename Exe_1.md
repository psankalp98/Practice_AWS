# Exercise 1

## OLTP
Online transactional processing enables the real-time execution of large numbers of database transactions by large numbers of people, typically over the internet. OLTP is what enables the rapid, accurate data processing behind ATMs and online banking, cash registers and ecommerce, and scores of other services we interact with each day.

## OLAP
Online analytical processing is software technology you can use to analyze business data from different points of view. Organizations collect and store data from multiple data sources, such as websites, applications, smart meters, and internal systems. OLAP combines and groups this data into categories to provide actionable insights for strategic planning. For example, a retailer stores data about all the products it sells, such as color, size, cost, and location. The retailer also collects customer purchase data, such as the name of the items ordered and total sales value, in a different system. OLAP combines the datasets to answer questions such as which color products are more popular or how product placement impacts sales.

## Differences between OLTP and OLAP
| Criteria | OLAP | OLTP |
| -------- | ------- | -------- |
| Purpose  | OLAP helps you analyze large volumes of data to support decision-making.| OLTP helps you manage and process real-time transactions. |
| Data source | OLAP uses historical and aggregated data from multiple sources.| OLTP uses real-time and transactional data from a single source. |
| Data structure | OLAP uses multidimensional (cubes) or relational databases.| OLTP uses relational databases. |
| Data model | OLAP uses star schema, snowflake schema, or other analytical models.| OLTP uses normalized or denormalized models. |
| Volume of data | OLAP has large storage requirements. Think terabytes (TB) and petabytes (PB). | OLTP has comparatively smaller storage requirements. Think gigabytes (GB). |
| Response time | OLAP has longer response times, typically in seconds or minutes. | OLTP has shorter response times, typically in milliseconds |
| Example applications | OLAP is good for analyzing trends, predicting customer behavior, and identifying profitability. | OLTP is good for processing payments, customer data management, and order processing. |


## Database Normal Forms
Normalization is the process of minimizing redundancy from a relation or set of relations. Redundancy in relation may cause insertion, deletion, and update anomalies. So, it helps to minimize the redundancy in relations. Normal forms are used to eliminate or reduce redundancy in database tables.
In database management systems (DBMS), normal forms are a series of guidelines that help to ensure that the design of a database is efficient, organized, and free from data anomalies. There are several levels of normalization, each with its own set of guidelines, known as normal forms.

First Normal Form (1NF): This is the most basic level of normalization. In 1NF, each table cell should contain only a single value, and each column should have a unique name. The first normal form helps to eliminate duplicate data and simplify queries.
Second Normal Form (2NF): 2NF eliminates redundant data by requiring that each non-key attribute be dependent on the primary key. This means that each column should be directly related to the primary key, and not to other columns.
Third Normal Form (3NF): 3NF builds on 2NF by requiring that all non-key attributes are independent of each other. This means that each column should be directly related to the primary key, and not to any other columns in the same table.
Boyce-Codd Normal Form (BCNF): BCNF is a stricter form of 3NF that ensures that each determinant in a table is a candidate key. In other words, BCNF ensures that each non-key attribute is dependent only on the candidate key.
Fourth Normal Form (4NF): 4NF is a further refinement of BCNF that ensures that a table does not contain any multi-valued dependencies.
Fifth Normal Form (5NF): 5NF is the highest level of normalization and involves decomposing a table into smaller tables to remove data redundancy and improve data integrity.


## Dimension vs Fact Table
| Parameters            | Fact Table                                                    | Dimension Table                                                |
|-----------------------|---------------------------------------------------------------|----------------------------------------------------------------|
| Basic                 | Contains quantitative data concerning business events         | Provides descriptive context and attributes for the data in the fact table |
| Sequence of creation  | Made after dimension table                                    | Created first                                                  |
| Components            | Facts, metrics and measurements                               | Descriptive attributes                                         |
| Quantity of components| Fewer attributes and more records                              | Fewer records and more attributes                              |
| Marked by             | Grain or atomic level                                          | Words, completeness, level of detail                           |
| Hierarchy             | Absent                                                        | Present                                                        |
| Location in Star schema | Middle                                                       | Edges                                                          |
| Purpose               | Analysis and decision making                                  | Data and process storage                                      |
| Growth                | Vertical                                                      | Horizontal                                                     |

## Types of Dimensions
- Slowly Changing Dimensions: Dimensions in data warehousing that capture changes in data over time with strategies like Type 1 (overwrite), Type 2 (historical tracking), or Type 3 (limited history) to maintain historical context.
- Rapidly Changing Dimensions: Dimensions in data warehousing that experience frequent changes, often requiring special handling to manage volatility and ensure accurate analysis.
- Junk Dimensions: Compact dimension tables in data warehousing that combine low-cardinality flags or indicators, reducing complexity by grouping miscellaneous or less critical attributes.
- Stacked Dimensions: A method in data warehousing where multiple dimensions are combined or "stacked" within a single dimension table, often used for efficiency in querying and analysis.
- Inferred Dimensions: Dimensions in data warehousing derived from existing data elements or relationships, allowing for deeper insights and analysis beyond explicitly defined dimensions.
- Conformed Dimensions: Standardized dimension tables shared across various data marts or data warehouses, ensuring uniform interpretation and analysis of data throughout an organization.
- Degenerate Dimensions: Data elements in a fact table that act as dimensions without having a separate dimension table, typically representing transactional or non-dimensional data such as invoice numbers.
- Role-Playing Dimensions: Dimensions in data warehousing that serve multiple analytical roles within the same data model, such as a "Date" dimension used for both order dates and delivery dates.
- Shrunken Dimensions: Dimension tables in data warehousing that are optimized or condensed, often by removing less frequently used attributes, to improve query performance and storage efficiency.
- Static Dimensions: Dimensions in data warehousing representing fixed or unchanging attributes, providing consistent reference points for analysis and reporting over time.

## Star Schema Vs Snowflake
| Star Schema                                                      | Snowflake Schema                                                |
|------------------------------------------------------------------|-----------------------------------------------------------------|
| Hierarchies for the dimensions are stored in the dimensional table. | Hierarchies are divided into separate tables.                  |
| It contains a fact table surrounded by dimension tables.         | One fact table surrounded by dimension tables which are in turn surrounded by dimension tables. |
| In a star schema, only single join creates the relationship between the fact table and any dimension tables. | A snowflake schema requires many joins to fetch the data. |
| Simple DB Design.                                                | Very Complex DB Design.                                        |
| Denormalized Data structure and query also run faster.            | Normalized Data Structure.                                     |
| High level of Data redundancy                                   | Very low-level data redundancy                                 |
| Single Dimension table contains aggregated data.                  | Data Split into different Dimension Tables.                    |
| Cube processing is faster.                                       | Cube processing might be slow because of the complex join.     |
| Offers higher performing queries using Star Join Query Optimization. | Tables may be connected with multiple dimensions.              |
|                                                                  | The Snowflake schema is represented by centralized fact table which unlikely connected with multiple dimensions. |

