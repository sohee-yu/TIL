//쿼리로 구현하려고 했던거 실패해서...ㅜㅜ JAVA로 backend 처리하도록 구현 해봄

```
List<aaaaaList> list = mapper.aaaaaList(VO)

int cnt =1 ;
for(int i =0; i < list.size(); i++){
    if(i>0){
        if(list.get(i).getA().equals(list.get(i-1).getA())
        &&list.get(i).getB().equals(list.get(i-1).getB()) && ...
        ){
            cnt ++;
            list.get(i-1).setCnt(null);
        }else{
            if(cnt > 1){
                for(int j=1; j<=cnt; j++){
                    if(j == cnt){
                        list.get(i-j).setCnt(String.valueOf(cnt));
                    }else{
                        list.get(i-j).setCnt(null);
                    }
                }//end of for
            }//end of if -이전 데이터 리스트 Cnt 컬럼에 알맞은 값을 넣어줌

            cnt =1;
        }// 비교조건 종료

        if(i == list.size()-1 && cnt > 1){ //리스트의 마지막 값 비교
            for(int j=0; j < cnt; j++){
                if(){
                    list.get(i-j).setCnt(String.valueOf(cnt));
                }else{
                    list.get(i-j).setCnt(null);
                }
            }
        }//end of if
    }//end of if(i>0)
}//end of for

```

- 간단해 보이지만, 실제로 짜는데는 좀 시간이 오래걸렸구..ㅜㅜ
- 리팩토링이 필요한것 같은 코드 인데 사실 생각나진 않아서 못함...
- if 조건문과 반복문만 사용했고 데이터의 값들이 크지 않을거 같아 메모리에 큰 영향도 없을거 같음.
- ( 쿼리로 해당 기능을 구현한다고 했을때가 더 메모리가 절약 되는가????)
- 이전 값들과 비교하고 이전 값들을 set 해줘야 해서 향상된 for 문 사용하지 않음...
