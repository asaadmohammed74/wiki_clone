Unlike the cell system of displaying coordinates shown in the client, world coordinates relate to an object's position on the screen when drawing screen overlays in DirectX. These coordinates are commonly used in the map system for displaying objects such as [effects and sounds](Files/DMap).

```cpp
void CGameMap::World2Cell(int iWorldX,int iWorldY,int& iCellX,int& iCellY)
{
 
	iWorldX	-=m_posOrigin.x;
	iWorldY	-=m_posOrigin.y;
 
	double dWorldX  =(double)iWorldX;
	double dWorldY  =(double)iWorldY;
	double dCellWidth   =(double)_CELL_WIDTH; // _CELL_WIDTH = 64
	double dCellHeight  =(double)_CELL_HEIGHT; // _CELL_HEIGHT = 32
 
	double dTemp0   =(1.0*dWorldX)/(1.0*dCellWidth) + (1.0*dWorldY)/(1.0*dCellHeight);
	double dTemp1   =(1.0*dWorldY)/(1.0*dCellHeight) - (1.0*dWorldX)/(1.0*dCellWidth);
	iCellX  =Double2Int(dTemp0);
	iCellY  =Double2Int(dTemp1);
}
void CGameMap::Cell2World(int iCellX,int iCellY,int& iWorldX,int& iWorldY)
{
	iWorldX	=_CELL_WIDTH*(iCellX-iCellY)/2+m_posOrigin.x; // _CELL_WIDTH = 64
	iWorldY	=_CELL_HEIGHT*(iCellX+iCellY)/2+m_posOrigin.y; // _CELL_HEIGHT = 32
}
int Double2Int(double dValue)
{
	if((int)(dValue+0.5) >(int)dValue)
		return int(dValue)+1;
	else
		return int(dValue);
}
```