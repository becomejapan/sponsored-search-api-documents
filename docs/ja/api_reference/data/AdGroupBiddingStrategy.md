# AdGroupBiddingStrategy
AdGroupBiddingStrategyオブジェクトは、入札方法を表します。

### Service
+ [AdGroupService](../services/AdGroupService.md)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>biddingStrategyId</td>
  <td>xsd:long</td>
  <td> 自動入札IDです。<br>※2017年11月15日以降は設定できません。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>biddingStrategyName</td>
  <td>xsd:string</td>
  <td>自動入札名です。<br>※50文字以内になります。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>biddingStrategyType</td>
  <td>enum <a href="./BiddingStrategyType.md">BiddingStrategyType</a></td>
  <td>自動入札タイプです。<br>※2017年11月15日以降は「NONE」のみ設定可能です。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>biddingStrategySource</td>
  <td>enum <a href="./BiddingStrategySource.md">BiddingStrategySource</a></td>
  <td>入札ソースです。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>biddingScheme</td>
  <td><a href="./BiddingScheme_nonBiddingStrategy.md">BiddingScheme</a><br> inherited <a href="./ManualCpcBiddingScheme.md">ManualCpcBiddingScheme</a><br> inherited <a href="./BudgetOptimizerBiddingScheme.md">BudgetOptimizerBiddingScheme </a><br> inherited <a href="./EnhancedCpcBiddingScheme_nonBiddingStrategy.md">EnhancedCpcBiddingScheme</a><br> inherited <a href="./PageOnePromotedBiddingScheme_nonBiddingStrategy.md">PageOnePromotedBiddingScheme </a><br> inherited <a href="./TargetCpaBiddingScheme_nonBiddingStrategy.md">TargetCpaBiddingScheme</a><br> inherited <a href="./TargetSpendBiddingScheme_nonBiddingStrategy.md">TargetSpendBiddingScheme</a><br> inherited <a href="./TargetRoasBiddingScheme_nonBiddingStrategy.md">TargetRoasBiddingScheme</a></td>
  <td>自動入札設定の詳細です。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>initialBid</td>
  <td>enum <a href="./Bid_AdGroup.md">Bid</a></td>
  <td>入札価格です。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br><i>Updatable</i></td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>parentBiddingStrategyConfigurations[0...n]</td>
  <td><a href="./AdGroupBiddingStrategy.md">AdGroupBiddingStrategy</a></td>
  <td>上位エンティティの入札設定です。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
