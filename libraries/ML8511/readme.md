##ML8711�p���C�u����
�{�v���O�����̓��s�X�Z�~�R���_�N�^��UV�Z���T�[ ML8511�p���C�u�����ł��B

## API
*void ml8511.init(int pin);
ML8511���o�͂���M����AD�ϊ�����[�q�̏��������s���܂��B
A0-A5���w�肵�Ă��������B

*void ml8511.get_val(float *data);
UV�̒l���擾���܂��B

#Sample Program

int ADCpin_AnalogUV = A0;

void setup() {
	Serial.begin(115200);
	ml8511.init(ADCpin_AnalogUV);
  
}

void loop() {
  float uv;
  
  ml8511.get_val(&uv);
  
  Serial.print("ML8511 UV = ");
  Serial.print_double((double)uv,0);
  Serial.println(" [mW/cm2]");
  Serial.println("");
  
  delay(500);
}





