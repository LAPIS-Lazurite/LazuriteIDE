I2C�����LCD�R���g���[�� ST7032i�𐧌䂷�邽�߂̃h���C�o�ł��B

�ȉ��̃R�[�h�ŏ�i�ɁuLazurite�v�̕\����
���i�Ɂu00-99�v�܂ł̐������0.5�b�ŃJ�E���g�A�b�v���܂��B

LazuriteIDE\Libraries�̃t�H���_�ɁAST7032�t�H���_���ƕۑ����Ă��������B
�ȉ��̃v���O�����œ���m�F�����Ă��邾���ŁA���C�u�����̑S�@�\�]���͍s���Ă��܂���B

void setup(){
	lcd.init();
    lcd.begin(8, 2,LCD_5x8DOTS);
    lcd.setContrast(30);
    lcd.print("Lazurite");
}

void loop(){
	static int i=0;
	uint8_t msg[16];
	Print.init(msg,sizeof(msg));
	if(i<10)
	{
		Print.p("0");
	}
	Print.l(i,DEC);
    lcd.setCursor(0, 1);
    lcd.print(msg);
	delay(500);
	i++;
	if(i>=100) i=0;
}

