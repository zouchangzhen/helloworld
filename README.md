# helloworld

在github做的一个实验

| phoneNum | 电话号码 | 必填 |
| :--- | :--- | :--- |
| money | 多少钱 | 必填 |
| id | 信息 | 传递 |

&lt;?xml version="1.0" encoding="UTF-8"?&gt;

&lt;rules&gt;

	&lt;rule id="1000000001" comment="财付通"&gt;

		&lt;agent company="SZ-NNK" business="RECHARGE-0000001" agent="1000000001" ValidRow="1" FileType="csv" SplitChar=","&gt;

			&lt;global&gt;

				&lt;replaces&gt;

					&lt;replace key="\`"&gt;&lt;/replace&gt;

				&lt;/replaces&gt;

			&lt;/global&gt;

			&lt;columns&gt;

				&lt;column index="0" title="处理时间" /&gt;

				&lt;column index="-1" title="代理商号" default="1000000001" /&gt;

				&lt;column index="-1" title="我方订单号" /&gt;

				&lt;column index="-1" title="发送订单号" /&gt;

				&lt;column index="1" title="代理订单号" /&gt;

				&lt;column index="10" title="充值号码" matcher="\d{11,12}" startsWith="0" replaceFirst=" "/&gt;

				&lt;column index="6" title="金额" rate="\*1" isMoneyFormat="true"&gt;

					&lt;replaces match="false"&gt;

						&lt;replace key=","&gt;&lt;/replace&gt;

						&lt;replace key="\."&gt;&lt;/replace&gt;

					&lt;/replaces&gt;

				&lt;/column&gt;

				&lt;column index="5" title="状态"&gt;

					&lt;replaces other="-1"&gt;

						&lt;replace key="用户已支付"&gt;1&lt;/replace&gt;

						&lt;replace key="转入退款"&gt;2&lt;/replace&gt;

					&lt;/replaces&gt;

				&lt;/column&gt;

			&lt;/columns&gt;

		&lt;/agent&gt;

		&lt;company SplitChar="," company="SZ-NNK" business="RECHARGE-0000001" agent="1000000001"&gt;

			&lt;global&gt;

				&lt;replaces&gt;

					&lt;replace key="'"&gt;&lt;/replace&gt;

				&lt;/replaces&gt;

			&lt;/global&gt;

			&lt;columns&gt;

				&lt;column index="0" title="处理时间" /&gt;

				&lt;column index="1" title="代理商号" /&gt;

				&lt;column index="3" title="我方订单号" /&gt;

				&lt;column index="-1" title="发送订单号" /&gt;

				&lt;column index="4" title="代理订单号" /&gt;

				&lt;column index="7" title="充值号码" startsWith="0" replaceFirst=" "/&gt;

				&lt;column index="10" title="金额" rate="\*1"  isMoneyFormat="true"&gt;

					&lt;replaces match="false"&gt;

						&lt;replace key=","&gt;&lt;/replace&gt;

						&lt;replace key="\."&gt;&lt;/replace&gt;

					&lt;/replaces&gt;

				&lt;/column&gt;

				&lt;column index="8" title="状态"&gt;

					&lt;replaces other="-1"&gt;

						&lt;replace key="成功"&gt;1&lt;/replace&gt;

						&lt;replace key="失败"&gt;-1&lt;/replace&gt;

						&lt;replace key="处理中"&gt;3&lt;/replace&gt;

						&lt;replace key="已退款"&gt;2&lt;/replace&gt;

					&lt;/replaces&gt;

				&lt;/column&gt;

				&lt;column index="10" title="金额" rate="\*1" isMoneyFormat="true"&gt;

					&lt;replaces match="false"&gt;

						&lt;replace key=","&gt;&lt;/replace&gt;

						&lt;replace key="\."&gt;&lt;/replace&gt;

					&lt;/replaces&gt;

				&lt;/column&gt;

				&lt;column index="13" title="运营商编号" /&gt;

				&lt;column index="14" title="渠道编号" /&gt;

				

			&lt;/columns&gt;

		&lt;/company&gt;

	&lt;/rule&gt;

&lt;/rules&gt;



