Software entities (such as classes, modules, and functions) should be open for extension but closed for modification.


---

```java
class InvoiceDao {
	private Invoice invoice;
	
	public InvoiceDao(Invoice invoice) {
		this.invoice = invoice;
	}

	public saveToDB() {
		// save to db
	}
}
```

Now we need to add extra function to save invoice to file

```java
class InvoiceDao {
	private Invoice invoice;
	
	public InvoiceDao(Invoice invoice) {
		this.invoice = invoice;
	}

	public saveToDB() {
		// save to db
	}

	public saveToFile(String filename) {
		// save to file
	}
}
```

This is not following Open/Close principle, as we are modifying the class, instead we should extend the class.

---

```java
interface InvoiceDao {
	public void save(Invoice invoice);
}
```

```java
class DatabaseInvoiceDao implements InvoiceDao {

	@Override
	public void save(Invoice invoice) {
		// save to db
	}
}
```

```java
class FileInvoiceDao implements InvoiceDao {

	@Override
	public void save(Invoice invoice) {
		// save to file
	}
}
```

