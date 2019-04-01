Also called the “type” ID, it's generally composed of the type of item (id/1000), the subtype (id/10%100), and the quality (id%10). The ID is often manipulated in the cases of equipment items; changing the subtype to raise or lower the item's required level and changing the quality are both common, changing the type is not.

Below is an example that only applies to equipment items and allows easy changes to the item's type, subtype, and quality.

```cs
public class ItemArchetype
{
	public int Id;
	public ItemArchetype(int id) { Id = id; }
	public int Quality { get { return Id%10; } set { Id = Id/10*10 + value; } }
	public int Subtype { get { return Id/10%100; } set { Id = Id/1000*1000 + value*10 + Quality; } }
	public int Type { get { return Id/1000; } set { Id = value*1000 + Id%1000; } }
}
```