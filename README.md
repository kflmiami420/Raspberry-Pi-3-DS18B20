# Raspberry-Pi-3-DS18B20-Temperature-Sensor
Raspberry Pi 3 DS18B20 Temperature Sensor    pre wired water proof sensor with 10k resistor across V+ &amp; Signal 



A problem has been reported with occasional hangs when reading the temperature file when using Raspbian. If you find you have the same problem, try replacing the function read_temp_raw with the code below. You will also need to add a line at the top of the file 'import subprocess'.

#-----------------------------------------------
def read_temp_raw():
	catdata = subprocess.Popen(['cat',device_file], stdout=subprocess.PIPE, stderr=subprocess.PIPE)
	out,err = catdata.communicate()
	out_decode = out.decode('utf-8')
	lines = out_decode.split('\n')
	return lines
	#----------------------------------------------
