# Read -20 : Django Models
# Django Models

# Overview
### Django web applications access and manage data through Python objects referred to as models. Models define the structure of stored data, including the field types and possibly also their maximum size, default values, selection list options, help text for documentation, label text for forms, etc. The definition of the model is independent of the underlying database — you can choose one of several as part of your project settings. Once you've chosen what database you want to use, you don't need to talk to it directly at all — you just write your model structure and other code, and Django handles all the dirty work of communicating with the database for you.


# Designing the LocalLibrary models
### Before you jump in and start coding the models, it's worth taking a few minutes to think about what data we need to store and the relationships between the different objects.


### We know that we need to store information about books (title, summary, author, written language, category, ISBN) and that we might have multiple copies available (with globally unique id, availability status, etc.). We might need to store more information about the author than just their name, and there might be multiple authors with the same or similar names. We want to be able to sort information based on book title, author, written language, and category.

### When designing your models, it makes sense to have separate models for every "object" (a group of related information). In this case, the obvious objects are books, book instances, and authors.

### You might also want to use models to represent selection-list options (e.g. like a drop down list of choices), rather than hard coding the choices into the website itself — this is recommended when all the options aren't known up front or may change. Obvious candidates for models, in this case, include the book genre (e.g. Science Fiction, French Poetry, etc.) and language (English, French, Japanese).

### Once we've decided on our models and field, we need to think about the relationships. Django allows you to define relationships that are one to one (`OneToOneField`), one to many (`ForeignKey`) and many to many (`ManyToManyField`).

### With that in mind, the UML association diagram below shows the models we'll define in this case (as boxes).

<img src='https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Models/local_library_model_uml.svg'>

### We've created models for the book (the generic details of the book), book instance (status of specific physical copies of the book available in the system), and author. We have also decided to have a model for the genre so that values can be created/selected through the admin interface. We've decided not to have a model for the `BookInstance:status` — we've hardcoded the values (`LOAN_STATUS`) because we don't expect these to change. Within each of the boxes, you can see the model name, the field names, and types, and also the methods and their return types.

### The diagram also shows the relationships between the models, including their multiplicities. The multiplicities are the numbers on the diagram showing the numbers (maximum and minimum) of each model that may be present in the relationship. For example, the connecting line between the boxes shows that Book and a Genre are related. The numbers close to the Genre model show that a book must have one or more Genres (as many as you like), while the numbers on the other end of the line next to the Book model show that a Genre can have zero or many associated books.

# Model definition

### Models are usually defined in an application's models.py file. They are implemented as subclasses of `django.db.models.Model`, and can include fields, methods and metadata. The code fragment below shows a "typical" model, named `MyModelName`:

```python
from django.db import models
from django.urls import reverse

class MyModelName(models.Model):
    """A typical class defining a model, derived from the Model class."""

    # Fields
    my_field_name = models.CharField(max_length=20, help_text='Enter field documentation')
    # …

    # Metadata
    class Meta:
        ordering = ['-my_field_name']

    # Methods
    def get_absolute_url(self):
        """Returns the URL to access a particular instance of MyModelName."""
        return reverse('model-detail-view', args=[str(self.id)])

    def __str__(self):
        """String for representing the MyModelName object (in Admin site etc.)."""
        return self.my_field_name

```
# Fields

### A model can have an arbitrary number of fields, of any type — each one represents a column of data that we want to store in one of our database tables. Each database record (row) will consist of one of each field value. Let's look at the example seen below:

```python
my_field_name = models.CharField(max_length=20, help_text='Enter field documentation')

```

### Our above example has a single field called `my_field_name`, of type `models.CharField` — which means that this field will contain strings of alphanumeric characters. The field types are assigned using specific classes, which determine the type of record that is used to store the data in the database, along with validation criteria to be used when values are received from an HTML form (i.e. what constitutes a valid value). The field types can also take arguments that further specify how the field is stored or can be used. In this case we are giving our field two arguments:


* `max_length=20 `— States that the maximum length of a value in this field is 20 characters.
* `help_text='Enter field documentation'` — helpful text that may be displayed in a form to help users understand how the field is used.

### The field name is used to refer to it in queries and templates. Fields also have a label, which is specified using the `verbose_name` argument (with a default value of None). If `verbose_name` is not set, the label is created from the field name by replacing any underscores with a space, and capitalizing the first letter (for example, the field `my_field_name` would have a default label of My field name when used in forms).

### The order that fields are declared will affect their default order if a model is rendered in a form (e.g. in the Admin site), though this may be overridden.


# COMMON FIELD ARGUMENTS
## The following common arguments can be used when declaring many/most of the different field types:

* `help_text`: Provides a text label for HTML forms (e.g. in the admin site), as described above.
* `verbose_name`: A human-readable name for the field used in field labels. If not specified, Django will infer the default verbose name from the field name.
* `default`: The default value for the field. This can be a value or a callable object, in which case the object will be called every time a new record is created.
* `null`: If `True`, Django will store blank values as `NULL` in the database for fields where this is appropriate (a `CharField` will instead store an empty string). The default is `False`.
* `blank`: If `True`, the field is allowed to be blank in your forms. The default is `False`, which means that Django's form validation will force you to enter a value. This is often used with `null=True`, because if you're going to allow blank values, you also want the database to be able to represent them appropriately.
* `choices`: A group of choices for this field. If this is provided, the default corresponding form widget will be a select box with these choices instead of the standard text field.
* `primary_key`: If `True`, sets the current field as the primary key for the model (A primary key is a special database column designated to uniquely identify all the different table records). If no field is specified as the primary key, Django will automatically add a field for this purpose. The type of auto-created primary key fields can be specified for each app in `AppConfig.default_auto_field` or globally in the `DEFAULT_AUTO_FIELD` setting.

# COMMON FIELD TYPES
## The following list describes some of the more commonly used types of fields.

* `CharField` is used to define short-to-mid sized fixed-length strings. You must specify the `max_length` of the data to be stored.
* `TextField` is used for large arbitrary-length strings. You may specify a `max_length` for the field, but this is used only when the field is displayed in forms (it is not enforced at the database level).
* `IntegerField` is a field for storing integer (whole number) values, and for validating entered values as integers in forms.
* `DateField` and `DateTimeField` are used for storing/representing dates and date/time information (as Python `datetime.date` and `datetime.date`time objects, respectively). These fields can additionally declare the (mutually exclusive) parameters `auto_now=True` (to set the field to the current date every time the model is saved), `auto_now_add` (to only set the date when the model is first created), and `default` (to set a default date that can be overridden by the user).
* `EmailField` is used to store and validate email addresses.
* `FileField` and `ImageField` are used to upload files and images respectively (the ImageField adds additional validation that the uploaded file is an image). These have parameters to define how and where the uploaded files are stored.
* `AutoField` is a special type of `IntegerField` that automatically increments. A primary key of this type is automatically added to your model if you don't explicitly specify one.
* `ForeignKey` is used to specify a one-to-many relationship to another database model (e.g. a car has one manufacturer, but a manufacturer can make many cars). The "one" side of the relationship is the model that contains the "key" (models containing a "foreign key" referring to that "key", are on the "many" side of such a relationship).
* `ManyToManyField` is used to specify a many-to-many relationship (e.g. a book can have several genres, and each genre can contain several books). In our library app we will use these very similarly to `ForeignKeys`, but they can be used in more complicated ways to describe the relationships between groups. These have the parameter `on_delete` to define what happens when the associated record is deleted (e.g. a value of `models.SET_NULL` would set the value to `NULL`).

# Metadata

## You can declare model-level metadata for your Model by declaring class Meta, as shown.

```python
class Meta:
    ordering = ['-my_field_name']

```
### One of the most useful features of this metadata is to control the default ordering of records returned when you query the model type. You do this by specifying the match order in a list of field names to the `ordering` attribute, as shown above. The ordering will depend on the type of field (character fields are sorted alphabetically, while date fields are sorted in chronological order). As shown above, you can prefix the field name with a minus symbol (-) to reverse the sorting order.

```python
ordering = ['title', '-pubdate']
```
### the books would be sorted alphabetically by title, from A-Z, and then by publication date inside each title, from newest to oldest.


```python
verbose_name = 'BetterName'
```
### Other useful attributes allow you to create and apply new "access permissions" for the model (default permissions are applied automatically), allow ordering based on another field, or to declare that the class is "abstract" (a base class that you cannot create records for, and will instead be derived from to create other models).

### Many of the other metadata options control what database must be used for the model and how the data is stored (these are really only useful if you need to map a model to an existing database).