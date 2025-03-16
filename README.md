# Bestsellers Implementation (CZ/EN)

## **CZ - Implementace Nejprodávanějšího zboží**

### **Popis**
Vaším úkolem je implementovat šablonu třídy `Bestsellers`, která sleduje prodeje produktů a umožňuje dotazy na jejich pořadí a počet prodaných kusů.

### **Rozhraní programu**
Třída `Bestsellers` je parametrizovaná typem `Product`, který slouží jako identifikátor výrobků. O `Product` je garantováno:
- Má copy konstruktor a operátor přiřazení.
- Má destruktor.
- Podporuje porovnávací operátory.
- Má implementovanou funkci `std::hash`.

Třída `Bestsellers` musí implementovat následující veřejné metody:

#### **Základní metody**
- `size_t products() const` – vrací počet druhů evidovaného zboží.
- `void sell(const Product& p, size_t amount)` – zaeviduje prodej `amount` kusů zboží `p`.
- `size_t rank(const Product& p) const` – vrací pořadí produktu dle prodeje (číslováno od 1). Pokud se více produktů prodalo stejně, pořadí může být libovolné.
- `const Product& product(size_t rank) const` – inverzní funkce k `rank`. Zajišťuje, že `product(rank(p)) == p` a `rank(product(r)) == r`.
- `size_t sold(size_t r) const` – vrací počet prodaných kusů produktu na daném místě v žebříčku.
- `size_t sold(size_t from, size_t to) const` – vrací součet prodaných kusů pro produkty mezi `from` a `to` (včetně obou okrajů). Pokud `to < from`, volání je neplatné.

#### **Bonusové metody** (volitelné)
- `size_t first_same(size_t r) const` – vrací nejnižší rank `r'`, kde `sold(r') == sold(r)`.
- `size_t last_same(size_t r) const` – vrací nejvyšší rank `r'`, kde `sold(r') == sold(r)`.
  - Tyto metody jsou použity pouze v bonusových testech.

#### **Ošetření chyb**
- Pokud je argument neplatný (rank mimo meze nebo neznámý produkt v `rank`), vyvolá `std::out_of_range`.

---

## **EN - Bestsellers Implementation**

### **Description**
Your task is to implement the `Bestsellers` class template, which tracks product sales and allows queries on their rankings and sales numbers.

### **Program Interface**
The `Bestsellers` class is parameterized by the `Product` type, which serves as the product identifier. The `Product` type is guaranteed to:
- Have a copy constructor and assignment operator.
- Have a destructor.
- Support comparison operators.
- Have an implemented `std::hash` function.

The `Bestsellers` class must implement the following public methods:

#### **Core Methods**
- `size_t products() const` – Returns the number of unique products tracked.
- `void sell(const Product& p, size_t amount)` – Registers the sale of `amount` units of product `p`.
- `size_t rank(const Product& p) const` – Returns the rank of a product based on sales (starting from 1). If multiple products have the same sales, ranking can be arbitrary.
- `const Product& product(size_t rank) const` – Inverse function to `rank`. Ensures `product(rank(p)) == p` and `rank(product(r)) == r`.
- `size_t sold(size_t r) const` – Returns the number of units sold for the product at rank `r`.
- `size_t sold(size_t from, size_t to) const` – Returns the total units sold for products ranked between `from` and `to` (inclusive). If `to < from`, the call is invalid.

#### **Bonus Methods** (Optional)
- `size_t first_same(size_t r) const` – Returns the lowest rank `r'` where `sold(r') == sold(r)`.
- `size_t last_same(size_t r) const` – Returns the highest rank `r'` where `sold(r') == sold(r)`.
  - These methods are only used in bonus tests.

#### **Error Handling**
- If an invalid argument is provided (out-of-bounds rank or unknown product in `rank`), it throws `std::out_of_range`.

---
This document describes the required functionality of the `Bestsellers` class in both Czech and English.


