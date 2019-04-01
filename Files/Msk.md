This file type is used in the client for 3D terrain objects (objects which can be rotated in 2.5D space) which contain a distinct pattern of transparency. The alpha mask file defines the transparency of the texture from a specific angle in 2D space. After the client loads the full MSK file as a buffer, it only checks for transparency using the following function (below).

```
BOOL CAlphaMask::IsTransparent(CMyPos posPoint)
{
	if	((posPoint.x < 0) ||
		(posPoint.y < 0) ||
		(posPoint.x >= m_sizeInfo.iWidth) ||
		(posPoint.y >= m_sizeInfo.iHeight))
		return true;
 
	int nIndex = posPoint.x + posPoint.y*m_sizeInfo.iWidth;
 
	int nByteOffset = 0; //要偏移几个Byte
	int nBitOffset = 0;  //的几个Bit
	nByteOffset = nIndex/8;
	nBitOffset = nIndex%8;
	BYTE* bData = m_pBuffer+nByteOffset;
 
 
	BYTE bMask = 1 << nBitOffset;
	if(bMask & *bData)
		return false;
	return true;
}
```