# 概要
## [Azure のネットワークについて](networking-overview.md)
## アーキテクチャ
### [仮想データセンター](/azure/architecture/vdc/networking-virtual-datacenter)
### [複数のネットワーク パスを使用した非対称ルーティング](../expressroute/expressroute-asymmetric-routing.md?toc=%2fazure%2fnetworking%2ftoc.json)
### [セキュリティで保護されたネットワーク設計](../best-practices-network-security.md?toc=%2fazure%2fnetworking%2ftoc.json)
### [ハブスポーク トポロジ](https://docs.microsoft.com/azure/architecture/reference-architectures/hybrid-networking/hub-spoke)
### [ネットワーク セキュリティのベスト プラクティス](../security/azure-security-network-security-best-practices.md?toc=%2fazure%2fnetworking%2ftoc.json)
### [可用性の高いネットワーク仮想アプライアンス](https://docs.microsoft.com/azure/architecture/reference-architectures/dmz/nva-ha )
### [負荷分散方法の組み合わせ](../traffic-manager/traffic-manager-load-balancing-azure.md?toc=%2fazure%2fnetworking%2ftoc.json)
### [Azure DNS と Traffic Manager を使用したディザスター リカバリー](disaster-recovery-dns-traffic-manager.md)
## 計画と設計
### [仮想ネットワーク](../virtual-network/virtual-network-vnet-plan-design-arm.md?toc=%2fazure%2fnetworking%2ftoc.json)
### [クロスプレミス接続 - VPN](../vpn-gateway/vpn-gateway-about-vpngateways.md?toc=%2fazure%2fnetworking%2ftoc.json)
### [クロスプレミス接続 - 専用プライベート](../expressroute/expressroute-workflows.md?toc=%2fazure%2fnetworking%2ftoc.json)
### バックエンド接続の相互運用性
#### [前書きとテスト セットアップ](connectivty-interoperability-preface.md?toc=%2fazure%2fnetworking%2ftoc.json)
#### [テスト セットアップの構成](connectivty-interoperability-configuration.md?toc=%2fazure%2fnetworking%2ftoc.json)
#### [コントロール プレーンの分析](connectivty-interoperability-control-plane.md?toc=%2fazure%2fnetworking%2ftoc.json)
#### [データ プレーンの分析](connectivty-interoperability-data-plane.md?toc=%2fazure%2fnetworking%2ftoc.json)

##  概念
### [仮想ネットワーク](../virtual-network/virtual-networks-overview.md?toc=%2fazure%2fnetworking%2ftoc.json)
### [ネットワークの負荷分散](../load-balancer/load-balancer-overview.md?toc=%2fazure%2fnetworking%2ftoc.json)
### [アプリケーションの負荷分散](../application-gateway/overview.md?toc=%2fazure%2fnetworking%2ftoc.json)
### [DNS](../dns/dns-overview.md?toc=%2fazure%2fnetworking%2ftoc.json)
### [DNS ベースのトラフィック分散](../traffic-manager/traffic-manager-overview.md?toc=%2fazure%2fnetworking%2ftoc.json)
### [オンプレミスへの接続 - VPN](../vpn-gateway/vpn-gateway-about-vpngateways.md?toc=%2fazure%2fnetworking%2ftoc.json)
### [オンプレミスへの接続 - 専用](../expressroute/expressroute-introduction.md?toc=%2fazure%2fnetworking%2ftoc.json)


# 作業開始
## [最初の仮想ネットワークの作成](../virtual-network/quick-create-portal.md?toc=%2fazure%2fnetworking%2ftoc.json)

# 方法
## インターネット接続
### [ネットワーク負荷分散パブリック サーバー](../load-balancer/load-balancer-get-started-internet-portal.md?toc=%2fazure%2fnetworking%2ftoc.json)
### [アプリケーション負荷分散パブリック サーバー](../application-gateway/quick-create-portal.md?toc=%2fazure%2fnetworking%2ftoc.json)
### [Web アプリケーションの保護](../application-gateway/application-gateway-web-application-firewall-portal.md?toc=%2fazure%2fnetworking%2ftoc.json)
### [場所に基づいた負荷分散](../traffic-manager/traffic-manager-configure-geographic-routing-method.md?toc=%2fazure%2fnetworking%2ftoc.json)
## 内部接続
### [ネットワーク負荷分散プライベート サーバー](../load-balancer/load-balancer-get-started-ilb-arm-portal.md?toc=%2fazure%2fnetworking%2ftoc.json)
### [アプリケーション負荷分散プライベート サーバー](../application-gateway/application-gateway-ilb-arm.md?toc=%2fazure%2fnetworking%2ftoc.json)
### [仮想ネットワークへの接続 (同じ場所)](../virtual-network/virtual-networks-create-vnetpeering-arm-portal.md?toc=%2fazure%2fnetworking%2ftoc.json)
### [仮想ネットワークへの接続 (異なる場所)](../vpn-gateway/vpn-gateway-howto-vnet-vnet-resource-manager-portal.md?toc=%2fazure%2fnetworking%2ftoc.json)
## クロスプレミス接続
### [S2S VPN 接続を作成する (IPsec/IKE)](../vpn-gateway/vpn-gateway-howto-site-to-site-resource-manager-portal.md?toc=%2fazure%2fnetworking%2ftoc.json)
### [P2S VPN 接続を作成する (SSTP と証明書)](../vpn-gateway/vpn-gateway-howto-point-to-site-resource-manager-portal.md?toc=%2fazure%2fnetworking%2ftoc.json)
### [専用プライベート接続を作成する (ExpressRoute)](../expressroute/expressroute-howto-circuit-portal-resource-manager.md?toc=%2fazure%2fnetworking%2ftoc.json)

## 管理
### [ネットワーク監視の概要](network-monitoring-overview.md)
### [リソースの使用量と Azure の上限との比較](check-usage-against-limits.md)
### [ネットワーク トポロジの表示](../network-watcher/network-watcher-topology-powershell.md?toc=%2fazure%2fnetworking%2ftoc.json)

## サンプルのスクリプト
### [Azure CLI](cli-samples.md)
### [Azure PowerShell](powershell-samples.md)

## チュートリアル
### [VM の負荷分散](../virtual-machines/linux/tutorial-load-balancer.md?toc=%2fazure%2fnetworking%2ftoc.json)
### [仮想ネットワークへのコンピューターの接続](../vpn-gateway/vpn-gateway-howto-point-to-site-resource-manager-portal.md?toc=%2fazure%2fnetworking%2ftoc.json)

# リファレンス
## [Azure CLI](https://docs.microsoft.com/cli/azure/network)
## [Azure PowerShell](https://docs.microsoft.com/powershell/module/azurerm.network/?view=azurermps-3.8.0)
## [.NET](https://docs.microsoft.com/dotnet/api/microsoft.azure.management.network?view=azuremgmtnetwork-9.1.0-preview)
## [Node.js](https://azure.microsoft.com/develop/nodejs/#azure-sdk)
## [REST](https://msdn.microsoft.com/library/mt163658.aspx)

# リソース
## [テンプレートの作成](/azure/azure-resource-manager/resource-group-authoring-templates?toc=%2fazure%2fnetworking%2ftoc.json)
## [Azure のロードマップ](https://azure.microsoft.com/roadmap/?category=networking)
## [コミュニティ テンプレート](https://azure.microsoft.com/resources/templates/)
## [ネットワークのブログ](https://azure.microsoft.com/blog/topics/networking)
## [料金](https://azure.microsoft.com/pricing)
## [料金計算ツール](https://azure.microsoft.com/pricing/calculator/)
## [リージョン別の提供状況](https://azure.microsoft.com/regions/services/)
## [Stack Overflow](http://stackoverflow.com/questions/tagged/azure-virtual-network)
## [ビデオ](https://azure.microsoft.com/resources/videos/index/?services=virtual-network)

