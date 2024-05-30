# Dust Effect Library

Dust Effect is a visual effect library for Android applications. This library adds impressive animations to the user interface by making elements explode off the screen.

## Example View
    ![View](https://github.com/kayamustafa33/Dust-Effect/assets/89656051/78c12d0d-fcf5-4080-8232-a0eb07ccbf1b)


## Usage

1. **Adding Dependencies**

    Add the following dependency to your Gradle script:

    ```gradle
    dependencies {
        implementation ("com.github.kayamustafa33:Dust-Effect:1.1")
    }
    ```

2. **Using the Library**

    ```kotlin
    // Importing the Dust Effect library
    import com.github.kayamustafa33.dusteffect.ExplosionField

    // Creating an instance of ExplosionField
    private var mExplosionField: ExplosionField? = null

    // Accessing the mExplosionField object within an Activity or Fragment
    // For example, to explode an item in a RecyclerView:
    mExplosionField = ExplosionField.attach2Window(activity)
    mExplosionField!!.explode(holder.itemView)

    // Clearing all explosions
    mExplosionField?.clear()
    ```

## Example Scenario: Deleting an Item from a List

Consider a scenario where items in a list are removed by exploding them. First, we need to add an explosion effect for each item.

```kotlin
// Using onClickListener within a RecyclerView.ViewHolder to delete the item
holder.itemView.setOnClickListener {
    // Exploding the item to delete it
    mExplosionField!!.explode(holder.itemView)
    // Deleting the item
    deleteItemFromList(holder.adapterPosition)
}
