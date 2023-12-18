## **ER Diagram Components**

![Alt text](image-1.png)

![Alt text](image-3.png)

1. **Rectangle (Entity)**
   - Represents a database table.
   - Example: Entity "Customer."

2. **Ellipse (Attribute)**
   - Represents entity attributes.
   - Connected to entity by a line.
   - Example: Attribute "Name" in "Customer."

3. **Diamond (Relationship)**
   - Signifies associations between entities.
   - Contains relationship name.
   - Example: "Purchases" connecting "Customer" and "Product."

4. **Double Ellipse (Multi-Valued Attribute)**
   - Indicates attributes with multiple values.
   - Example: "Phone Numbers" in "Customer."

5. **Double Rectangle (Weak Entity)**
   - Represents an entity dependent on another.
   - Connected by a double diamond.
   - Example: "Order" weak entity in "Customer."

6. **Oval (Derived Attribute)**
   - Represents calculated attributes.
   - Example: Derived attribute "Age" in "Employee."

7. **Dashed Oval (Key Attribute)**
   - Signifies key attributes.
   - Example: Dashed oval around "CustomerID" in "Customer."

8. **Double Rectangle (Weak Entity)**
   - Represents a weak entity.
   - Example: "Order" weak entity in "Customer."

9. **Double Diamond (Aggregation)**
   - Represents higher-level entity composition.
   - Example: "Department" composed of "Employee."

10. **Dashed Line (Partial Participation)**
    - Indicates optional entity participation.
    - Example: Dashed line for partial participation of "Product" in "Manufactures."

11. **Double Dashed Line (Total Participation)**
    - Represents mandatory entity participation.
    - Example: Double dashed line for total participation of "Department" in "Manages."

12. **Arrow (Cardinality)**
    - Shows relationship cardinality.
    - Examples: "1" (One), "M" (Many), "0" (Zero).
    - Example: "One-to-Many" relationship arrow.

![Alt text](image-2.png)

13. **Generalization/Specialization (Triangle)**
    - Represents entity hierarchy.
    - Example: "Animal" generalization to "Mammal" and "Bird."

14. **Dashed Line with Arrow (Inheritance)**
    - Shows inheritance in hierarchies.
    - Example: Dashed line with arrow from "Employee" to "Manager."