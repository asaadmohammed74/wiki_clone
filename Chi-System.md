Enumerators for being used with Chi System. Packet Structures will be sent later and I'll update here with the links.
# Chi Attributes
Attributes that can be achieved by the Chi System. Remember that for saving space in the database, you can save the **ChiAttributeType*10000 + ChiPower** as a integer.
```cs
public enum TrainingVitalityAttributeType
{
	None = 0,
	CriticalStrike = 1,
	SkillCriticalStrike = 2,
	Immunity = 3,
	Breakthrough = 4,
	Counteraction = 5,
	Health = 6,
	Attack = 7,
	MagicAttack = 8,
	MDefense = 9,
	FinalAttack = 10,
	FinalMagicAttack = 11,
	DamageReduction = 12,
	MagicDamageReduction = 13
}
``` 
# Chi Stages
The four stages that the user can unlock.
```cs
public enum TrainingVitalityStage
{
	None = 0,
	Dragon = 1,
	Phoenix = 2,
	Tiger = 3,
	Turtle = 4
}
```
# Instructions
## Saving the lock positions for stages
When the user sends a request for refreshing the values you also receive an offset with the locked position which the system will not update. That values can be saved into the database and they are sent to the client as a 16 bit integer.
You can use 1 ushort for storing it somewhere in the database or do whatever you please to save this information, but this need to be sent as ONE number back to the client, so your player wont need to always be locking his Chi Attributes before updating.
```cs
MsgTrainingVitalityInfo msg = new MsgTrainingVitalityInfo
{
	Type = (ushort) (update ? 1 : 0),
	ChiPoints = owner.ChiPoints,
	UserIdentity = owner.Identity,
	Flags = 0
};
foreach (var chi in m_myChi.Values)
{
	/** 
		here you append your flags. Remember:
		Offset: 0-3 Dragon, 4-7 Tiger and etc.
	*/
	msg.Flags |=  (uint)((int)chi.Entity.StageLock << 4*(((int)chi.Mode)-1));
	msg.Append((byte) chi.Mode, chi.Entity.Power1, chi.Entity.Power2, 
		chi.Entity.Power3, chi.Entity.Power4);
}
```
This way your player can always open the Chi window with his attributes locked like the last way he updated it, and you wont need to see they complaining about accidental attributes changes because your Chi System doesn't work the way it should.