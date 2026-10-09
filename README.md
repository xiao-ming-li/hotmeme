[indet.html](https://github.com/user-attachments/files/33241915/indet.html)
<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no">
<title>热梗填词 · 250题挑战</title>
<style>
*{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent}
body{font-family:-apple-system,'PingFang SC','Microsoft YaHei',sans-serif;
background:linear-gradient(160deg,#0f1a2b,#1b2c40);min-height:100vh;
display:flex;justify-content:center;align-items:center;padding:12px;color:#eef4ff}
.app{max-width:480px;width:100%;background:rgba(20,30,45,.8);backdrop-filter:blur(16px);
border-radius:28px;padding:20px 16px;box-shadow:0 30px 60px rgba(0,0,0,.8);
border:1px solid rgba(255,255,255,.06);position:relative}
h1{text-align:center;font-size:1.5rem;font-weight:600;letter-spacing:1px;
color:#d0e2ff;margin-bottom:4px;display:flex;align-items:center;justify-content:center;gap:8px}
h1 span{font-size:1.4rem}
.subhead{text-align:center;font-size:.75rem;color:#7d95af;margin-bottom:14px;
font-style:italic;border-bottom:1px dashed rgba(140,180,230,.15);padding-bottom:10px}
.status-bar{display:flex;justify-content:space-between;align-items:center;
background:rgba(0,0,0,.3);border-radius:16px;padding:10px 14px;margin-bottom:14px;
border:1px solid rgba(255,255,255,.04);font-size:.85rem}
.status-item{display:flex;align-items:center;gap:6px;color:#a8c4e0}
.status-item .val{color:#ffd966;font-weight:700;font-size:1rem}
.progress-wrap{flex:1;margin:0 12px;height:6px;background:#1a2c3d;border-radius:3px;overflow:hidden}
.progress-bar{height:100%;background:linear-gradient(90deg,#4e7aa0,#6fcf97);
border-radius:3px;transition:width .4s ease;width:0%}
.game-card{background:rgba(0,0,0,.35);border-radius:22px;padding:24px 14px 18px;
margin-bottom:14px;border:1px solid rgba(255,255,255,.05);
box-shadow:inset 0 4px 12px rgba(0,0,0,.5)}
.question-text{font-size:1.8rem;font-weight:700;display:flex;flex-wrap:wrap;
align-items:center;justify-content:center;gap:4px 6px;margin-bottom:22px;
min-height:3.5rem;text-shadow:0 2px 8px rgba(0,0,0,.5);letter-spacing:1px;text-align:center}
.blank-slot{display:inline-block;min-width:80px;padding:0 4px;
border-bottom:4px solid #5f8ec0;color:#ffd966;font-weight:700;text-align:center;
transition:all .2s;font-size:1.8rem;line-height:1.4}
.blank-slot.filled{border-bottom-color:#6fcf97;color:#e6ffb3}
.options-grid{display:flex;flex-direction:column;gap:10px;margin-top:8px}
.option-btn{background:#1f3448;border:1.5px solid #2e4b66;border-radius:16px;
padding:14px 18px;font-size:1.15rem;font-weight:500;color:#e3efff;cursor:pointer;
transition:all .1s;box-shadow:0 4px 0 #0b141e,0 6px 14px rgba(0,0,0,.4);
letter-spacing:.5px;text-align:center;font-family:inherit}
.option-btn:hover:not(:disabled){background:#2c4a66;transform:translateY(-1px);
box-shadow:0 5px 0 #0b141e,0 8px 18px rgba(0,0,0,.5)}
.option-btn:active:not(:disabled){transform:translateY(3px);box-shadow:0 1px 0 #0b141e}
.option-btn.correct{background:#276b46;border-color:#6fcf97;
box-shadow:0 2px 0 #0f2e1e,0 4px 12px rgba(0,200,100,.3);transform:translateY(2px)}
.option-btn.incorrect{background:#7a2e2e;border-color:#e57373;
box-shadow:0 2px 0 #3e1414,0 4px 12px rgba(220,80,80,.3);transform:translateY(2px)}
.option-btn:disabled{opacity:.75;cursor:not-allowed;transform:translateY(2px);
box-shadow:0 2px 0 #0b141e}
.feedback-msg{text-align:center;font-size:1rem;margin:12px 0 4px;min-height:2.5rem;
color:#b8d4ff;padding:6px;border-radius:12px;transition:all .2s}
.feedback-msg.correct{color:#a5ffc0}
.feedback-msg.wrong{color:#ffb0b0}
.btn-row{display:flex;gap:10px;justify-content:center;margin-top:10px;flex-wrap:wrap}
.btn{border:none;border-radius:14px;padding:12px 24px;font-size:1rem;font-weight:600;
color:#f0f7ff;cursor:pointer;transition:all .07s;letter-spacing:.5px;
font-family:inherit;flex:1;min-width:120px}
.btn-primary{background:#4d6d8f;box-shadow:0 4px 0 #1c2d3d,0 6px 16px rgba(0,0,0,.4)}
.btn-primary:hover:not(:disabled){background:#5f83a8;transform:translateY(-1px)}
.btn-primary:active:not(:disabled){transform:translateY(3px);box-shadow:0 1px 0 #1c2d3d}
.btn-primary:disabled{opacity:.4;cursor:not-allowed;transform:translateY(2px);
box-shadow:0 2px 0 #1c2d3d}
.btn-ad{background:#8b5a2b;box-shadow:0 4px 0 #3e2410,0 6px 16px rgba(0,0,0,.4)}
.btn-ad:hover:not(:disabled){background:#a86e36}
.btn-ad:active:not(:disabled){transform:translateY(3px);box-shadow:0 1px 0 #3e2410}
.btn-reset{background:#414e5a;box-shadow:0 4px 0 #1f262c,0 6px 16px rgba(0,0,0,.4)}
.btn-reset:hover{background:#525f6b}
.admin-panel{background:rgba(10,20,30,.7);border-radius:18px;padding:14px;
margin-top:14px;border:1px solid #2e4a5e}
.admin-header{display:flex;justify-content:space-between;align-items:center;
cursor:pointer;user-select:none;color:#b8cde0;font-weight:500;font-size:.9rem}
.admin-content{display:none;margin-top:12px;border-top:1px solid #2e4a5e;padding-top:12px}
.admin-content.open{display:block}
.form-row{display:flex;flex-direction:column;gap:4px;margin-bottom:10px}
.form-row label{font-size:.8rem;color:#9bb5d0}
.form-row input,.form-row textarea{background:#152433;border:1px solid #2f4f6b;
border-radius:10px;padding:10px 12px;color:#eef4ff;font-size:.95rem;
font-family:inherit;outline:none;transition:border .2s}
.form-row input:focus,.form-row textarea:focus{border-color:#6a9ed0}
.form-row textarea{min-height:60px;resize:vertical}
.hint{font-size:.72rem;color:#7d95af;margin-top:-6px;margin-bottom:8px}
.bank-list{max-height:150px;overflow-y:auto;margin-top:8px}
.bank-item{display:flex;justify-content:space-between;align-items:center;
background:#132433;border-radius:10px;padding:8px 10px;margin-bottom:6px;
font-size:.8rem;border-left:4px solid #4a7aa0;gap:6px;flex-wrap:wrap}
.bank-item .q-text{color:#c8ddf5;flex:1;word-break:break-all;min-width:100px}
.bank-item .q-answer{color:#ffd966;font-weight:600}
.del-btn{background:#5a2e2e;border:none;border-radius:8px;color:#ffc6c6;
padding:4px 10px;font-size:.75rem;cursor:pointer;font-family:inherit}
.del-btn:hover{background:#7a3e3e}
.empty-bank{color:#7a8f9f;font-style:italic;text-align:center;padding:10px;font-size:.85rem}
.reward-popup{position:fixed;top:0;left:0;right:0;bottom:0;
background:rgba(0,0,0,.8);display:none;justify-content:center;align-items:center;
z-index:999;padding:20px;backdrop-filter:blur(4px)}
.reward-popup.show{display:flex}
.reward-box{background:linear-gradient(145deg,#1e3448,#152433);border-radius:24px;
padding:32px 24px;max-width:320px;width:100%;text-align:center;
border:2px solid #6fcf97;box-shadow:0 0 40px rgba(100,220,150,.3);
animation:popIn .3s ease}
@keyframes popIn{0%{transform:scale(.8);opacity:0}100%{transform:scale(1);opacity:1}}
.reward-box .emoji{font-size:3rem;margin-bottom:12px}
.reward-box h3{color:#a5ffc0;font-size:1.3rem;margin-bottom:8px}
.reward-box p{color:#b8d4ff;font-size:.9rem;margin-bottom:18px;line-height:1.6}
.reward-box .btn{width:100%;margin-top:8px}
.modal-popup{position:fixed;top:0;left:0;right:0;bottom:0;
background:rgba(0,0,0,.75);display:none;justify-content:center;align-items:center;
z-index:998;padding:20px}
.modal-popup.show{display:flex}
.modal-box{background:#1b2c40;border-radius:20px;padding:28px 22px;max-width:300px;
width:100%;text-align:center;border:1px solid #4a6a8a}
.modal-box h3{color:#ffd966;font-size:1.2rem;margin-bottom:10px}
.modal-box p{color:#a8c4e0;font-size:.9rem;margin-bottom:20px;line-height:1.5}
.toast{position:fixed;bottom:30px;left:50%;transform:translateX(-50%);
background:rgba(0,0,0,.85);color:#eef4ff;padding:10px 20px;border-radius:20px;
font-size:.85rem;z-index:1000;opacity:0;transition:opacity .3s;pointer-events:none}
.toast.show{opacity:1}
</style>
</head>
<body>
<div class="app">
  <h1><span>🔥</span>热梗填词<span>🧩</span></h1>
  <div class="subhead">250题挑战 · 你认得几个梗？</div>
  <div class="status-bar">
    <div class="status-item">⚡<span class="val" id="staminaDisplay">50</span></div>
    <div class="progress-wrap"><div class="progress-bar" id="progressBar"></div></div>
    <div class="status-item">📝<span class="val" id="progressDisplay">0/0</span></div>
  </div>
  <div class="game-card" id="gameCard">
    <div class="question-text" id="questionDisplay">加载中...</div>
    <div class="options-grid" id="optionsContainer"></div>
    <div class="feedback-msg" id="feedbackMsg"></div>
    <div class="btn-row">
      <button class="btn btn-primary" id="nextBtn" disabled>下一题 →</button>
    </div>
  </div>
  <div class="admin-panel">
    <div class="admin-header" id="adminToggle">
      <span>⚙️ 后台管理 · 添加热梗</span>
      <span id="toggleIcon">➕</span>
    </div>
    <div class="admin-content" id="adminContent">
      <div class="form-row">
        <label>完整梗（例如：尊嘟假嘟）</label>
        <input type="text" id="newFullMeme" placeholder="输入完整梗">
      </div>
      <div class="form-row">
        <label>要挖空的答案（例如：假）</label>
        <input type="text" id="newAnswer" placeholder="输入要挖空的字/词">
      </div>
      <div class="hint">💡 代码会自动把答案从梗里挖掉，生成填空题</div>
      <button class="btn btn-primary" id="addBtn" style="width:100%;margin-top:4px">➕ 添加</button>
      <div style="margin-top:12px">
        <div style="color:#b0c8e0;font-size:.85rem;margin-bottom:6px">📚 题库（<span id="bankCount">0</span>题）</div>
        <div class="bank-list" id="bankList"></div>
      </div>
      <button class="btn btn-reset" id="resetBankBtn" style="width:100%;margin-top:10px;font-size:.85rem;padding:8px">🔄 重置题库</button>
    </div>
  </div>
  <div class="reward-popup" id="rewardPopup">
    <div class="reward-box">
      <div class="emoji" id="rewardEmoji">🎉</div>
      <h3 id="rewardTitle">恭喜通关！</h3>
      <p id="rewardText">你完成了5道题，获得10体力！</p>
      <button class="btn btn-primary" id="rewardClose">继续挑战</button>
    </div>
  </div>
  <div class="modal-popup" id="staminaModal">
    <div class="modal-box">
      <h3>⚡ 体力不足</h3>
      <p>看一段广告，立即获得 <b style="color:#ffd966">6</b> 点体力</p>
      <div class="btn-row">
        <button class="btn btn-ad" id="watchAdBtn">📺 看广告</button>
        <button class="btn btn-reset" id="cancelAdBtn">取消</button>
      </div>
    </div>
  </div>
  <div class="toast" id="toast"></div>
</div>
<script>
(function(){
'use strict';
const DEFAULT_RAW_LIST = [
  ["尊嘟假嘟","假"],["泰裤辣","辣"],["栓Q","Q"],["City不City","好"],["班味","味"],
  ["显眼包","包"],["搭子","搭"],["情绪价值","价值"],["松弛感","松弛"],["小孩哥","哥"],
  ["硬控","控"],["水灵灵","灵"],["偷感","偷"],["红温","温"],["那咋了","咋"],
  ["搞抽象","抽象"],["丝瓜汤","瓜"],["活人感","活人"],["谷子","谷"],["苏超","超"],
  ["南方小土豆","土豆"],["科目三","三"],["多巴胺穿搭","多巴胺"],["美拉德","拉德"],["酱香拿铁","拿铁"],
  ["命运的齿轮","齿轮"],["确认过眼神","眼神"],["退退退","退"],["海克斯科技","海克斯"],["雪糕刺客","刺客"],
  ["羊了个羊","羊"],["我是云南的","云南"],["恐龙扛狼","狼"],["没病走两步","走"],["鸡你太美","鸡"],
  ["奥利给","利给"],["淡黄的长裙","长裙"],["蓝瘦香菇","香菇"],["老六","六"],["YYDS","DS"],
  ["绝绝子","子"],["破防了","防"],["内卷","卷"],["躺平","躺"],["凡尔赛","尔赛"],
  ["打工人","工人"],["干饭人","饭"],["后浪","浪"],["神兽","兽"],["集美","美"],
  ["耗子尾汁","尾汁"],["不讲武德","武德"],["小丑竟是我自己","小丑"],["蚌埠住了","蚌埠"],["夺笋啊","笋"],
  ["社死","社"],["爷青回","青回"],["双厨狂喜","双厨"],["泪目","泪"],["有内味了","味"],
  ["瑞思拜","拜"],["真香","香"],["我太难了","难"],["柠檬精","柠檬"],["杠精","杠"],
  ["键盘侠","键盘"],["吃瓜群众","瓜"],["锦鲤","鲤"],["佛系","佛"],["硬核","硬"],
  ["沙雕","沙"],["戏精","戏"],["C位","C"],["天花板","天花板"],["割韭菜","韭菜"],
  ["薅羊毛","羊毛"],["上岸","岸"],["吃土","土"],["土味情话","土味"],["舔狗","狗"],
  ["海王","海"],["鱼塘","鱼"],["绿茶","绿茶"],["白莲花","莲花"],["圣母","圣母"],
  ["云玩家","云"],["肝帝","肝"],["氪金","氪"],["欧皇","欧"],["非酋","非"],
  ["脱非入欧","欧"],["豹子头","豹子"],["零充","零"],["首充","首"],["月卡党","月卡"],
  ["白嫖","嫖"],["真香定律","香"],["打工魂","魂"],["干饭魂","魂"],["工具人","工具"],
  ["小确幸","幸"],["断舍离","断舍"],["极简主义","极简"],["社恐","恐"],["社牛","牛"],
  ["i人","i"],["e人","e"],["浓人","浓"],["淡人","淡"],["搭子文化","搭子"],
  ["饭搭子","饭"],["旅游搭子","旅游"],["健身搭子","健身"],["学习搭子","学习"],["摸鱼搭子","摸鱼"],
  ["脆皮大学生","脆皮"],["特种兵旅游","特种兵"],["淄博烧烤","烧烤"],["尔滨","滨"],["砂糖橘","橘"],
  ["小当归","当归"],["海底捞科目三","科目三"],["佛山电翰","电翰"],["闻神","闻神"],["于文亮","文亮"],
  ["东北雨姐","雨姐"],["疯狂小杨哥","小杨哥"],["李佳琦","佳琦"],["花西子","西子"],["哪里贵了","贵"],
  ["找找自己原因","原因"],["工资涨没涨","涨"],["79元眉笔","79"],["国货崛起","国货"],["蜂花","蜂花"],
  ["鸿星尔克","尔克"],["白象","白象"],["汇源","汇源"],["活力28","活力"],["郁美净","美净"],
  ["莲花味精","莲花"],["精心","精心"],["雪王","雪王"],["蜜雪冰城","雪"],["瑞幸","瑞幸"],
  ["茅台","茅台"],["联名","联名"],["喜茶","喜茶"],["周杰伦","杰伦"],["演唱会","演唱会"],
  ["TFBOYS","TF"],["十周年","十周年"],["西安","西安"],["帝国灯牌","灯牌"],["抢票","抢票"],
  ["黄牛","黄牛"],["强实名","实名"],["退票","退票"],["五月天","五月天"],["假唱","假唱"],
  ["垫音","垫音"],["半开麦","半开麦"],["村超","村超"],["村BA","村BA"],["贵州","贵州"],
  ["榕江","榕江"],["台盘村","台盘"],["淄博","淄博"],["烧烤专列","专列"],["进淄赶烤","赶烤"],
  ["八大局","大局"],["绿豆糕","绿豆糕"],["炒锅饼","锅饼"],["紫米饼","紫米"],["哈尔滨","哈尔滨"],
  ["冰雪大世界","冰雪"],["冻梨","冻梨"],["摆盘","摆盘"],["小砂糖橘","砂糖橘"],["野生菌","菌"],
  ["小菌主","菌主"],["云南","云南"],["泼水节","泼水"],["火把节","火把"],["村晚","村晚"],
  ["英歌舞","英歌"],["社火","社火"],["打铁花","铁花"],["簪花","簪花"],["泉州","泉州"],
  ["蟳埔村","蟳埔"],["洛阳","洛阳"],["汉服","汉服"],["马面裙","马面"],["新中式","新中式"],
  ["围炉煮茶","围炉"],["露营","露营"],["飞盘","飞盘"],["骑行","骑行"],["天水","天水"],
  ["麻辣烫","麻辣烫"],["开封","开封"],["王婆说媒","王婆"],["相亲","相亲"],["彩礼","彩礼"],
  ["婚恋","婚恋"],["精神内耗","内耗"],["发疯文学","发疯"],["废话文学","废话"],["鼠鼠文学","鼠鼠"],
  ["孔乙己文学","孔乙己"],["骆驼祥子","祥子"],["祥子","祥子"],["脱不下的长衫","长衫"],["学历是我下不来的高台","高台"],
  ["孔乙己","孔乙己"],["茴字有四种写法","茴字"],["回字","回字"],["站着喝酒","站着"],["穿长衫","长衫"],
  ["短衣帮","短衣"],["长衫客","长衫"],["丁举人","丁举人"],["打折腿","打折"],["窃书","窃书"],
  ["读书人的事","读书人"],["能算偷么","偷"],["君子固穷","君子"],["者乎","者乎"],["多乎哉","多乎"],
  ["不多也","不多"],["茴香豆","茴香"],["一人一颗","一颗"],["罩住","罩住"],["碟子","碟子"],
  ["教给你","教"],["做掌柜","掌柜"],["写账","写账"],["污人清白","清白"],["跌断","跌断"],
  ["大约的确死了","死了"],["韧性","韧性"],["具身智能","具身"],["赛博对账","对账"],["数字游民","游民"],
  ["敬自己一杯","敬"],["助我破鼎","破鼎"],["如何呢又能怎","又能怎"],["村咖","村咖"],["竟然人","竟然"],
  ["居然人","居然"],["办公室李小冉","李小冉"],["数理花","数理"],["姐感妹","姐感"],["妹感姐","妹感"],
  ["三明治拒绝法","三明治"],["爱你老己","老己"],["我的刀盾","刀盾"],["咕咕嘎嘎","嘎嘎"],["酱板鸭","板鸭"],
  ["邪修","邪修"],["米塔","米塔"],["晓燕劝学","劝学"],["呆猫","呆猫"],["春晚机器人","机器人"],
  ["神之一指","一指"],["社交的手腕","手腕"],["视奸","视奸"],["所有人坐下","坐下"],["阿达西雄鹰","雄鹰"],
  ["大展宏图","宏图"],["玉面手雷王","手雷"],["世纪大和解","和解"],["灵感菇","灵感"],["用户彻底怒了","怒了"],
  ["彩虹六号解禁","解禁"],["绊爱归来","绊爱"],["田叔","田叔"],["数学锐锐","锐锐"],["我老爸得了MVP","MVP"],
  ["三角洲行动","三角洲"],["Speed中国行","Speed"],["哈基米音乐","哈基米"],["芦毛灰姑娘","灰姑娘"],["凸变英雄","凸变"],
  ["魔女与使魔","使魔"],["GTA6跳票","跳票"],["gogogo出发咯","出发"],["人生呐能不能放过我","放过我"],["把你的心给我","心给我"],
  ["末日后酒店","酒店"],["超级上海保卫战","保卫战"],["擎天柱","擎天柱"],["赛博难民","难民"],["拼好晚","拼好"],
  ["提灯定损","提灯"],["举报一手","举报"],["潘宏训猪","训猪"],["驯化大数据","驯化"],["被村里人包围了","包围"],
  ["阿诺文学","阿诺"],["TGA公式","TGA"],["咽食症","咽食"],["拼尽全力也无法战胜","战胜"],["太好了是xx","太好了"],
  ["业主群闹事头像","头像"],["清华健身房","健身房"],["熏鸡事变","熏鸡"],["如何分辨狼和狗","狼和狗"],["UZI捧杯","捧杯"],
  ["借你号玩玩","借号"],["变异酒馆","酒馆"],["对宁谈墙","谈墙"],["乙游大世界","乙游"],["大学生防沉迷","防沉迷"],
  ["何炅异食癖","异食癖"],["认祖归洲","归洲"],["六星街里还传来巴扬琴声","巴扬琴"]
];
let rawList = [], questionBank = [], currentIndex = 0, currentQuestion = null;
let isAnswered = false, stamina = 30, completedCount = 0;
let rewardedMilestones = {1:false,5:false,10:false,20:false,50:false,100:false};
const STAMINA_COST = 3, INIT_STAMINA = 50;
const REWARDS = {
  5:{stamina:5,emoji:'🔥',text:'完成5题！奖励5体力'},
  10:{stamina:10,emoji:'⭐',text:'完成10题！奖励10体力'},
  20:{stamina:15,emoji:'💎',text:'完成20题！奖励15体力'},
  50:{stamina:25,emoji:'👑',text:'完成50题！奖励25体力'},
  100:{stamina:40,emoji:'🏆',text:'完成100题！奖励40体力'},
};
const $ = id => document.getElementById(id);
const staminaDisplay=$('staminaDisplay'),progressDisplay=$('progressDisplay'),progressBar=$('progressBar');
const questionDisplay=$('questionDisplay'),optionsContainer=$('optionsContainer'),feedbackMsg=$('feedbackMsg');
const nextBtn=$('nextBtn'),adminToggle=$('adminToggle'),adminContent=$('adminContent'),toggleIcon=$('toggleIcon');
const newFullMeme=$('newFullMeme'),newAnswer=$('newAnswer'),addBtn=$('addBtn');
const bankList=$('bankList'),bankCount=$('bankCount'),resetBankBtn=$('resetBankBtn');
const rewardPopup=$('rewardPopup'),rewardEmoji=$('rewardEmoji'),rewardTitle=$('rewardTitle'),rewardText=$('rewardText'),rewardClose=$('rewardClose');
const staminaModal=$('staminaModal'),watchAdBtn=$('watchAdBtn'),cancelAdBtn=$('cancelAdBtn'),toast=$('toast');

function shuffle(arr){const a=[...arr];for(let i=a.length-1;i>0;i--){const j=Math.floor(Math.random()*(i+1));[a[i],a[j]]=[a[j],a[i]];}return a;}
function showToast(msg,dur=1800){toast.textContent=msg;toast.classList.add('show');clearTimeout(toast._t);toast._t=setTimeout(()=>toast.classList.remove('show'),dur);}
function escapeHtml(str){return String(str).replace(/[&<>"]/g,m=>{if(m==='&')return'&amp;';if(m==='<')return'&lt;';if(m==='>')return'&gt;';if(m==='"')return'&quot;';return m;});}

function buildQuestionBank(list){
  const allAnswers=list.map(item=>item[1]).filter(a=>a);
  return list.map(([fullMeme,answer])=>{
    if(!fullMeme||!answer)return null;
    const idx=fullMeme.indexOf(answer);
    if(idx===-1)return null;
    const template=fullMeme.slice(0,idx)+'()'+fullMeme.slice(idx+answer.length);
    const pool=allAnswers.filter(a=>a!==answer);
    const distractors=shuffle(pool).slice(0,2);
    while(distractors.length<2)distractors.push(['？','！','…','#','@'][distractors.length]||'？');
    return{template,answer,distractors};
  }).filter(Boolean);
}

function saveAll(){try{localStorage.setItem('hotMemeRawList',JSON.stringify(rawList));localStorage.setItem('hotMemeStamina',stamina);localStorage.setItem('hotMemeCompleted',completedCount);localStorage.setItem('hotMemeMilestones',JSON.stringify(rewardedMilestones));}catch(e){}}

function loadAll(){
  try{
    const savedRaw=localStorage.getItem('hotMemeRawList');
    if(savedRaw){const parsed=JSON.parse(savedRaw);rawList=Array.isArray(parsed)&&parsed.length>0?parsed:JSON.parse(JSON.stringify(DEFAULT_RAW_LIST));}
    else rawList=JSON.parse(JSON.stringify(DEFAULT_RAW_LIST));
    const s=localStorage.getItem('hotMemeStamina');stamina=s!==null?parseInt(s,10)||INIT_STAMINA:INIT_STAMINA;
    const c=localStorage.getItem('hotMemeCompleted');completedCount=c!==null?parseInt(c,10)||0:0;
    const m=localStorage.getItem('hotMemeMilestones');
    if(m){const mm=JSON.parse(m);if(mm&&typeof mm==='object')rewardedMilestones={...rewardedMilestones,...mm};}
  }catch(e){rawList=JSON.parse(JSON.stringify(DEFAULT_RAW_LIST));stamina=INIT_STAMINA;completedCount=0;}
}

function updateStatusBar(){
  staminaDisplay.textContent=stamina;
  const total=questionBank.length;
  progressDisplay.textContent=`${completedCount}/${total}`;
  progressBar.style.width=total>0?Math.min(100,(completedCount/total)*100)+'%':'0%';
}

function loadQuestionByIndex(idx){
  if(questionBank.length===0){questionDisplay.textContent='题库为空';optionsContainer.innerHTML='';return;}
  if(idx>=questionBank.length)idx=0;
  currentIndex=idx;
  const q=questionBank[currentIndex];currentQuestion=q;
  isAnswered=false;feedbackMsg.textContent='';feedbackMsg.className='feedback-msg';nextBtn.disabled=true;
  const template=q.template;
  if(template.includes('()')){
    const parts=template.split('()');
    if(parts.length>=2){
      const before=parts[0],after=parts.slice(1).join('');
      questionDisplay.innerHTML=`${escapeHtml(before)}<span class="blank-slot" id="blankSlot">______</span>${escapeHtml(after)}`;
    }else questionDisplay.innerHTML=escapeHtml(template);
  }else questionDisplay.innerHTML=escapeHtml(template);
  const options=shuffle([q.answer,...q.distractors]);
  optionsContainer.innerHTML='';
  options.forEach(opt=>{
    const btn=document.createElement('button');
    btn.className='option-btn';btn.textContent=opt;btn.dataset.value=opt;
    btn.addEventListener('click',onOptionClick);
    optionsContainer.appendChild(btn);
  });
  updateStatusBar();
}

function onOptionClick(e){
  if(isAnswered)return;
  if(stamina<STAMINA_COST){staminaModal.classList.add('show');return;}
  isAnswered=true;
  const selectedBtn=e.currentTarget,selectedValue=selectedBtn.dataset.value,correctAnswer=currentQuestion.answer;
  stamina-=STAMINA_COST;
  const blankSlot=$('blankSlot');
  if(blankSlot){blankSlot.textContent=selectedValue;blankSlot.classList.add('filled');}
  const allOptions=document.querySelectorAll('.option-btn');
  allOptions.forEach(btn=>btn.disabled=true);
  if(selectedValue===correctAnswer){
    selectedBtn.classList.add('correct');
    feedbackMsg.textContent='✅ 正确！';feedbackMsg.className='feedback-msg correct';
  }else{
    selectedBtn.classList.add('incorrect');
    allOptions.forEach(btn=>{if(btn.dataset.value===correctAnswer)btn.classList.add('correct');});
    feedbackMsg.textContent=`❌ 错啦！正确答案是「${correctAnswer}」`;feedbackMsg.className='feedback-msg wrong';
  }
  completedCount++;
  checkMilestones();
  nextBtn.disabled=false;updateStatusBar();saveAll();
}

function checkMilestones(){
  const milestones=[1,5,10,20,50,100];
  for(const m of milestones){
    if(completedCount>=m&&!rewardedMilestones[m]){
      rewardedMilestones[m]=true;
      const r=REWARDS[m];stamina+=r.stamina;
      showReward(r.emoji,r.text);saveAll();return;
    }
  }
}

function showReward(emoji,text){
  rewardEmoji.textContent=emoji;rewardTitle.textContent='🎊 恭喜！';rewardText.textContent=text;
  rewardPopup.classList.add('show');
}

function goToNextQuestion(){
  if(questionBank.length===0)return;
  if(stamina<STAMINA_COST){staminaModal.classList.add('show');return;}
  loadQuestionByIndex((currentIndex+1)%questionBank.length);
}

function renderBankList(){
  bankCount.textContent=rawList.length;
  if(rawList.length===0){bankList.innerHTML='<div class="empty-bank">题库为空</div>';return;}
  let html='';
  rawList.forEach((item,idx)=>{
    html+=`<div class="bank-item"><span class="q-text">${escapeHtml(item[0])}</span><span class="q-answer">${escapeHtml(item[1])}</span><button class="del-btn" data-index="${idx}">删</button></div>`;
  });
  bankList.innerHTML=html;
  bankList.querySelectorAll('.del-btn').forEach(btn=>{
    btn.addEventListener('click',e=>{
      const i=parseInt(e.target.dataset.index,10);
      if(!isNaN(i)&&i>=0&&i<rawList.length){rawList.splice(i,1);rebuildBank();saveAll();}
    });
  });
}

function rebuildBank(){
  questionBank=buildQuestionBank(rawList);
  if(questionBank.length===0)questionBank=[{template:'栓()',answer:'Q',distractors:['A','B']}];
  if(currentIndex>=questionBank.length)currentIndex=0;
  loadQuestionByIndex(currentIndex);renderBankList();updateStatusBar();
}

function addNewMeme(){
  const full=newFullMeme.value.trim(),ans=newAnswer.value.trim();
  if(!full||!ans){showToast('请填写完整梗和答案');return;}
  if(!full.includes(ans)){showToast('答案必须包含在完整梗里！');return;}
  rawList.push([full,ans]);rebuildBank();saveAll();
  newFullMeme.value='';newAnswer.value='';showToast('✅ 添加成功');
}

function init(){
  loadAll();
  questionBank=buildQuestionBank(rawList);
  if(questionBank.length===0)questionBank=[{template:'栓()',answer:'Q',distractors:['A','B']}];
  currentIndex=0;loadQuestionByIndex(0);renderBankList();updateStatusBar();
  nextBtn.addEventListener('click',goToNextQuestion);
  adminToggle.addEventListener('click',()=>{adminContent.classList.toggle('open');toggleIcon.textContent=adminContent.classList.contains('open')?'➖':'➕';});
  addBtn.addEventListener('click',addNewMeme);
  resetBankBtn.addEventListener('click',()=>{
    if(confirm('确定重置题库为默认吗？所有自定义题目会丢失')){
      rawList=JSON.parse(JSON.stringify(DEFAULT_RAW_LIST));stamina=INIT_STAMINA;completedCount=0;
      rewardedMilestones={1:false,5:false,10:false,20:false,50:false,100:false};
      rebuildBank();saveAll();showToast('已重置');
    }
  });
  rewardClose.addEventListener('click',()=>rewardPopup.classList.remove('show'));
  watchAdBtn.addEventListener('click',()=>{stamina+=6;updateStatusBar();saveAll();staminaModal.classList.remove('show');showToast('📺 广告观看完成 +6体力');});
  cancelAdBtn.addEventListener('click',()=>staminaModal.classList.remove('show'));
  [newFullMeme,newAnswer].forEach(inp=>{inp.addEventListener('keypress',e=>{if(e.key==='Enter'){e.preventDefault();addNewMeme();}});});
}
init();
})();
</script>
</body>
</html>
