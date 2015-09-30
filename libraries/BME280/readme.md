#BME280
Lazurite��BOSH�� �����x�^�C���Z���T�[ BME280����f�[�^���擾���邽�߂̃��C�u�����ł��B

#�g����
bme280�̃t�H���_��LazuriteIDE\Libraries�̃t�H���_�ɃR�s�[���Ă��������B
bme280.init(CSB�[�q�̔ԍ�) ��BME280�����������܂��B
bme280.read(double *temp, double *humi, double *press)�Ńf�[�^���擾���܂��B
temp, humi, press�́A���ꂼ�ꉷ�x�^���x�^�C���̃f�[�^���i�[����double�^�̃|�C���^���w�肵�Ă��������B
�|�C���^�̈�����NULL���w�肵���ꍇ�A�Ώۂ̒l�͎擾���܂���B

#�T���v���R�[�h
�T���v���R�[�h�ł́A�擾�������x�^���x�^�C���̃f�[�^���V���A���ŏo�͂��܂��B

------��������------

#define BME280_CSB 10

void setup()
{
	
	Serial.begin(115200);
	bme280.init(BME280_CSB);
}


void loop()
{
    double temp_act = 0.0, press_act = 0.0,hum_act=0.0;
    
	bme280.read(&temp_act, &hum_act, &press_act);
	
    Serial.print("TEMP : ");
    Serial.print_double(temp_act,2);
    Serial.print(" DegC  PRESS : ");
    Serial.print_double(press_act,2);
    Serial.print(" hPa  HUM : ");
    Serial.print_double(hum_act,2);
    Serial.println(" %");
	
	sleep(1000);
}





