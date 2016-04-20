##BM1423�p���C�u����
�{�v���O�����̓��[�����n���C�Z���T�[ BM1423�p�̃��C�u�����ł��B

## API
*void bm1423.init(int slave_address);
BM1423�̏��������s���܂��Bslave_address��0x0F��ݒ肷���BME1423�̃X���[�u�A�h���X��0x0F�ɂ��ē��삵�܂��B����ȊO�̎���slave_address��0x0E�ɂȂ�܂��B
����Ɋ��������0��Ԃ��܂��B

*byte bm1423.get_val(float *data);
�n���C�Z���T�[�̒l���擾���܂��Bdata�ɂ́A3��float�^�z��̐擪�|�C���^���w�肵�Ă��������B����Ɋ��������0��Ԃ��܂��B


#Sample Program
void setup() {
  byte rc;

  Serial.begin(115200);
  
  Wire.begin();
  
  rc = bm1423.init(0);
}

void loop() {
  byte rc;
  float mag[3];
  rc = bm1423.get_val(mag);

  if (rc == 0) {
    Serial.print("BM1423 XDATA=");
    Serial.println_double(mag[0], 2);
    Serial.print("BM1423 YDATA=");
    Serial.println_double(mag[1], 2);
    Serial.print("BM1423 ZDATA=");
    Serial.println_double(mag[2], 2);
    Serial.print("\n");    
  }
  
  delay(500);
}


