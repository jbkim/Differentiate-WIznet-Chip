Differentiate-WIznet-Chip
=========================
How to differntiate WIZnet Chip, W5100, W5200 and W5500 in Arduino code?

<pre>
uint8_t W5500Class::getVersionTest(void)
{
		uint8_t _data;

	  // W5200
	  setSS();  
	  SPI.transfer(0x00);
	  SPI.transfer(0x1F);
	  SPI.transfer(0x00);
	  SPI.transfer(0x01); 
	  _data = SPI.transfer(0);
	  resetSS();
    if (_data == 0x03) return 0x03;

	// W5500
    setSS();
    SPI.transfer(0x00);
    SPI.transfer(0x39);
    SPI.transfer(0x00);
    _data = SPI.transfer(0);
    resetSS();
    if (_data == 0x04) return 0x04;
    	else return _data;

}	
</pre>



Testing with WebServer.ino code
