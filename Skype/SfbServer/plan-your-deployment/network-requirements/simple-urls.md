---
title: 서버의 단순 URL에 대한 DNS 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: '요약: 이 항목의 단순 URL 고려 사항을 검토한 후 이 항목의 DNS 레코드를 구현하기 전에 비즈니스용 Skype 서버.'
ms.openlocfilehash: a36805566b7bdb9f95ef14b572a8efdccdeb916b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622140"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>서버의 단순 URL에 대한 DNS 비즈니스용 Skype 서버

**요약:** URL에 대한 DNS 레코드를 구현하기 전에 이 항목의 단순 URL 고려 사항을 비즈니스용 Skype 서버.

단순 URL을 사용하면 사용자가 모임에 쉽게 참가할 수 있으며, 관리자가 비즈니스용 Skype 서버 도구를 보다 쉽게 사용할 수 있습니다. 단순 URL은 정의한 SIP 도메인과 일치하지 않는 자체 도메인을 사용하게 됩니다. 

비즈니스용 Skype 서버, 전화 접속 및 관리자의 세 가지 단순 URL을 지원할 수 있습니다. Meet 및 Dial-In에 대해 단순 URL을 설정해야 하며 관리 단순 URL은 선택 사항입니다. 단순 URL을 지원하는 데 필요한 DNS(Domain Name System) 레코드는 이러한 단순 URL을 정의한 방법 및 단순 URL에 대해 재해 복구를 지원할지 여부에 따라 다릅니다. 

## <a name="simple-url-scope"></a>단순 URL 범위

전역 범위에서 적용되도록 단순 URL을 구성하거나 조직의 각 중앙 사이트에 대해 서로 다른 단순 URL을 지정할 수 있습니다. 전역 단순 URL과 사이트 단순 URL이 둘 다 지정된 경우에는 사이트 단순 URL이 우선적으로 적용됩니다. 

대부분의 경우 단순 URL은 전역 수준에서만 설정하여 한 사이트에서 다른 사이트로 이동하는 경우 사용자의 Meet 단순 URL이 변경되지 않는 것이 좋습니다. 단, 여러 사이트의 전화 접속 사용자에 서로 다른 전화 번호를 사용해야 하는 조직은 예외입니다. 사이트에서 하나의 단순 URL(예: 전화 접속 단순 URL)을 사이트 수준 단순 URL로 설정한 경우에는 해당 사이트의 다른 단순 URL도 사이트 수준으로 설정해야 합니다.

토폴로지 작성기에서 전역 단순 URL을 설정할 수 있습니다. 사이트 수준에서 단순 URL을 설정하기 위해 Set-CsSimpleURLConfiguration cmdlet을 사용합니다.

단순 URL을 정의하려면 DNS 구성에서 A 및/또는 AAAA 레코드를 설정해야 합니다.

## <a name="simple-url-naming-and-validation-rules"></a>단순 URL 이름 지정 및 유효성 검사 규칙
<a name="BK_Valid"> </a>

토폴로지 작성기 및 비즈니스용 Skype 서버 관리 셸 cmdlet은 단순 URL에 대해 여러 유효성 검사 규칙을 적용합니다. 모임 및 전화 접속 단순 URL은 필수 설정이지만 관리 단순 URL은 선택 사항입니다. 모임 단순 URL은 SIP 도메인마다 별도의 URL이 있어야 하지만 전화 접속 단순 URL과 관리 단순 URL은 전체 조직에 하나만 있으면 됩니다.

조직의 각 단순 URL에는 고유한 이름이 있어야 하지만 다른 단순 URL의 SfB2015.contoso.com/Meet 수 없습니다. 예를 들어 SfB2015.contoso.com/Meet 단순 URL로 설정할 수 SfB2015.contoso.com/Meet/Dialin URL로 설정할 수 없습니다. 단순 URL 이름에는 풀의 FQDN 또는 포트 정보(예: 허용되지 않습니다.)가 https://FQDN:88/meet 포함될 수 없습니다. 모든 단순 URL은 https:// 접두사로 시작해야 합니다. 

단순 URL은 영숫자(즉, a-z, A-Z, 0-9 및 마침표(.))만 포함할 수 있습니다. 다른 문자를 사용하면 단순 URL이 예상대로 작동하지 않을 수 있습니다.

## <a name="changing-simple-urls-after-deployment"></a>배포 후 단순 URL 변경
<a name="BK_Valid"> </a>

초기 배포 후 단순 URL을 변경하려면 단순 URL의 DNS 레코드 및 인증서가 이러한 변경으로 인해 받을 수 있는 영향을 파악해야 합니다. 단순 URL의 기준이 변경되면 DNS 레코드 및 인증서도 변경해야 합니다. 예를 들어 기본 URL을 SfB2015.contoso.com meet.contoso.com 변경하기 때문에 DNS 레코드 및 인증서를 변경하여 기본 https://SfB2015.contoso.com/Meet https://meet.contoso.com URL을 meet.contoso.com. 단순 URL을 에서 로 변경한 경우 기본 URL SfB2015.contoso.com 동일하게 유지되어 DNS 또는 인증서를 변경할 필요가 https://SfB2015.contoso.com/Meet https://SfB2015.contoso.com/Meetings 없습니다.

그러나 단순 URL 이름을 변경할 때마다 각 Director 및 프런트 엔드 서버에서 **Enable-CsComputer를** 실행하여 변경을 등록해야 합니다.

## <a name="naming-examples-for-simple-urls"></a>단순 URL의 이름 이름 예제
<a name="BK_Valid"> </a>

단순 URL의 이름을 지정할 때 권장되는 세 가지 옵션이 있습니다. 선택한 옵션에 따라 단순 URL을 지원하는 DNS A 레코드 및 인증서 설정 방법이 결정됩니다. 각 옵션에서는 조직의 각 SIP 도메인에 대해 하나의 모임 단순 URL을 구성해야 합니다. 

보유한 SIP 도메인 수에 관계없이 전화 접속 단순 URL과 관리 단순 URL은 항상 전체 조직에서 각각 하나씩만 있으면 됩니다.

옵션 1에서는 각 단순 URL에 대한 새 SIP 도메인 이름을 만듭니다.

이 옵션을 사용하는 경우 각 단순 URL에 대해 별도의 DNS A 레코드가 필요하며 각 모임 단순 URL의 이름이 인증서에 지정되어 있어야 합니다.

**단순 URL 이름 지정 옵션 1**


| **단순 URL** <br/> | **예** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | https://meet.contoso.com, https://meet.fabrikam.com 등(조직의 각 SIP 도메인에 대해 하나씩)  <br/> |
| 전화 접속  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| 관리자  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

옵션 2에서는 단순 URL이 도메인 이름 및 도메인 SfB2015.contoso.com. 따라서 세 가지 유형의 단순 URL을 모두 사용할 수 있는 DNS A 레코드가 하나만 필요합니다. 이 DNS A 레코드는 SfB2015.contoso.com. 또한 조직의 다른 SIP 도메인에 대해 별도의 DNS A 레코드가 필요합니다. 

**단순 URL 이름 지정 옵션 2**


| **단순 URL** <br/> | **예** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meet 등(조직의 각 SIP 도메인에 대해 하나씩)  <br/> |
| 전화 접속  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| 관리자  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

옵션 3은 많은 SIP 도메인이 있고 각각에 별도의 모임 단순 URL을 사용하지만 이러한 단순 URL에 필요한 DNS 레코드 및 인증서를 최소화하려는 경우에 가장 유용합니다. 

**단순 URL 이름 지정 옵션 3**


| **단순 URL** <br/> | **예** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| 전화 접속  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| 관리자  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>단순 URL에 대한 재해 복구 옵션
<a name="BK_Valid"> </a>

프런트 엔드 풀이 포함된 사이트가 여러 개 있으며 DNS 공급자가 GeoDNS를 지원하는 경우 재해 복구를 지원하기 위해 단순 URL에 대한 DNS 레코드를 설정하여 전체 프런트 엔드 풀이 다운되어도 단순 URL 기능이 계속 제공될 수 있습니다. 이 재해 복구 기능은 모임 및 전화 접속 단순 URL을 지원합니다.

이와 같이 구성하려면 GeoDNS 주소 두 개를 만듭니다. 각 주소에는 재해 복구용으로 쌍으로 지정된 두 개의 풀로 확인되는 DNS A 또는 CNAME 레코드 두 개가 포함됩니다. GeoDNS 주소 중 하나는 내부 액세스용으로 사용되며, 두 풀에 대한 내부 웹 FQDN 또는 부하 분산 장치 IP 주소로 확인됩니다. 나머지 GeoDNS 주소는 외부 액세스용으로 사용되며, 두 풀의 외부 웹 FQDN 또는 부하 분산 장치 IP 주소로 확인됩니다. 아래에는 풀의 FQDN을 사용하는 모임 단순 URL의 예가 나와 있습니다. 

```console
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```console
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

그런 후에 meet.contoso.com과 같은 모임 단순 URL을 두 개의 GeoDNS 주소로 확인하는 CNAME 레코드를 만듭니다.

> [!NOTE]
> 네트워크에서 헤어핀(조직 내부에서 생성되는 트래픽을 비롯하여 모든 단순 URL 트래픽을 외부 링크를 통해 라우팅)을 사용하는 경우에는 외부 GeoDNS 주소만 구성하고 모임 단순 URL을 해당 외부 주소로만 확인할 수 있습니다.

이 방법을 사용하는 경우 각 GeoDNS 주소가 라운드 로빈 방법을 사용하여 요청을 두 풀로 분산시키거나, 기본적으로 한 풀(예: 지리적으로 더 가까이 있는 풀)에 연결하고 다른 풀은 연결 오류 시에만 사용하도록 구성할 수 있습니다. 

전화 접속 단순 URL에 대해 같은 구성을 설정할 수 있습니다. 이렇게 하여 이전 예제의 레코드와 같은 추가 레코드를 만들어 DNS 레코드에  `dialin` `meet` 대신합니다. 관리 단순 URL의 경우 이 섹션 앞부분에 나와 있는 세 가지 옵션 중 하나를 사용합니다.

이 구성을 설정한 후에는 모니터링 응용 프로그램을 사용하여 오류를 감시할 HTTP 모니터링을 설정해야 합니다. 외부 액세스의 경우 HTTPS GET lyncdiscover가 있는지 모니터링합니다.<sipdomain> 두 풀에 대한 외부 웹 FQDN 또는 부하 조정기 IP 주소에 대한 요청이 성공적입니다. 예를 들어 다음 요청은 **ACCEPT** 헤더를 포함하면 안 되며 **200 OK** 를 반환해야 합니다.

```console
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

내부 액세스의 경우에는 두 풀에 대해 내부 웹 FQDN 또는 부하 분산 장치 IP 주소에서 포트 5061을 모니터링해야 합니다. 연결 오류가 감지되면 이러한 풀의 VIP가 포트 80, 443 및 4443을 닫아야 합니다.


