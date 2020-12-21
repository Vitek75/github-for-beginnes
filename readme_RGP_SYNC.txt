RGP_sync 
При запуске подтягивает справочники result_SPR <= select * from spr.srts_spr_notes
Пишет логи об ошибках в  NODEJS.W_SERVER_LOG, а middle_log пишет в NODEJS.W_HTTP_LOG
условие на выборку ВУ и СРТС на отправку DATE_DISP > (trunc(SYSDATE)-1) and TYPE_NOT in ('PROIZV', 'SENT_APK', 'APK_ACCEPT') and CONNECT_ID is null 

Запросы к базе находятся в модуле db-queries.js, line 80
формирование json-пакета на отправку в РГП в модуле model_create.js, Line 17

метод отправки:
const axios = require('axios');
res = await axios.post(url, SrtsJson);
 if (res.status == '200') {
                        if (res.data.status == true) {
                            Cg.cnf.showlog && console.log('UpdateCard srts ID_M ' + card.result_SRTS[i].ID_M)
                            UpdStatus = await db_queries.UpdateCard(oracledb, 'update kon.nfox_con set   CONNECT_ID= :CONNECT_ID where ID_M= :ID_M', { "CONNECT_ID": "1", "ID_M": card.result_SRTS[i].ID_M });
                       если ошибка отправки пакета, пишет в NODEJS.W_SERVER_LOG


            Url_srts_ph: 'http://192.168.7.233:31707/cpsvrc',
            Url_srts_jur: 'http://192.168.7.233:31707/cpsvrcle',
            Url_vu: 'http://192.168.7.233:31707/cpsdl',
            App_Name: 'app_sync'
        }
        db_options = {
            user: 'nodejs',
            password: 'Eb*4OznfU?s1',
            connectString: '192.168.7.212:1521/orcl',
            poolMax: 25,
            poolMin: 25,
            poolIncrement: 0
        };
        single_db_options = {
            user: 'nodejs',
            password: 'Eb*4OznfU?s1',
            connectString: '192.168.7.212:1521/orcl',
        };