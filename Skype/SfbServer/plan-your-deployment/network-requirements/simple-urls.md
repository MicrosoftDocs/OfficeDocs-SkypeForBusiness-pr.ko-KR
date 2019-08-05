---
title: 비즈니스용 Skype 서버의 간단한 Url에 대 한 DNS 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: '요약: 비즈니스용 Skype 서버에 대 한 DNS 레코드를 구현 하기 전에이 항목의 간단한 URL 고려 사항을 검토 하세요.'
ms.openlocfilehash: 6f5003542f797c6dd275eb8de7c0b00b1ea209ac
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196854"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 간단한 Url에 대 한 DNS 요구 사항

**요약:** 비즈니스용 Skype 서버에 대 한 DNS 레코드를 구현 하기 전에이 항목의 간단한 URL 고려 사항을 검토 하세요.

간단한 Url을 사용 하면 사용자에 게 보다 쉽게 모임에 참가할 수 있으며, 관리자는 비즈니스용 Skype 서버 관리 도구를 사용 하는 것이 더 쉬워졌습니다. 간단한 Url은 사용자가 정의한 SIP 도메인과 일치 하지 않는 자체 도메인을 사용 합니다. 

비즈니스용 Skype 서버는 회의, 전화 접속 및 관리자의 세 가지 간단한 Url을 지원 합니다. 시작 및 전화 접속에 대 한 간단한 Url을 설정 해야 하며, 관리자 단순 URL은 선택 사항입니다. 간단한 url을 지원 하기 위해 필요한 DNS (Domain Name System) 레코드는 간단한 url을 정의한 방법과 간단한 Url에 대 한 재해 복구를 지원 하는지 여부에 따라 달라 집니다. 

## <a name="simple-url-scope"></a>간단한 URL 범위

전역 범위를 포함 하도록 간단한 Url을 구성 하거나 조직의 각 중앙 사이트에 대해 서로 다른 간단한 Url을 지정할 수 있습니다. 전역 단순 URL과 사이트 단순 URL이 모두 지정 된 경우 사이트 단순 URL이 우선권을 갖습니다. 

대부분의 경우 사용자가 한 사이트에서 다른 사이트로 이동 하는 경우 단순한 URL이 변경 되지 않도록 전역 수준 에서만 간단한 Url을 설정 하는 것이 좋습니다. 이 예외는 다른 사이트의 전화 접속 사용자에 게 다른 전화 번호를 사용 해야 하는 조직입니다. 사이트의 간단한 URL (예: 전화 접속 간단한 URL)을 사이트 수준 간단한 URL로 설정한 경우에는 해당 사이트의 다른 간단한 url도 사이트 수준으로 설정 해야 합니다.

토폴로지 작성기에서 전역 단순 Url을 설정할 수 있습니다. 사이트 수준에서 간단한 URL을 설정 하려면 Set-CsSimpleURLConfiguration cmdlet을 사용 합니다.

간단한 URL을 정의 하는 경우 DNS 구성에서 A 및/또는 AAAA 레코드를 설정 해야 할 수도 있습니다.

## <a name="simple-url-naming-and-validation-rules"></a>간단한 URL 명명 및 유효성 검사 규칙
<a name="BK_Valid"> </a>

토폴로지 작성기 및 비즈니스용 Skype 서버 관리 셸 cmdlet은 간단한 Url에 대 한 여러 가지 유효성 검사 규칙을 적용 합니다. 간단한 Url을 시작 및 전화 접속으로 설정 해야 하지만 관리자 용으로 설정 하는 것은 선택 사항입니다. 각 SIP 도메인에는 별도의 단순 URL이 필요 하지만, 전체 조직에 대해 하나의 전화 접속 단순 url과 하나의 관리자 단순 URL만 있으면 됩니다.

조직의 각 단순 URL은 고유한 이름을 가져야 하 고 다른 간단한 URL의 접두사가 될 수 없습니다 (예를 들어, SfB2015.contoso.com/Meet를 사용 하 여 단순한 url로 시작 하 고 SfB2015.contoso.com/Meet/Dialin를 전화 접속 간단한 URL로 설정할 수 없습니다). 간단한 URL 이름에는 풀의 FQDN 또는 포트 정보 (예: 허용 되지 않음) https://FQDN:88/meet 가 포함 될 수 없습니다. 모든 단순 Url은 https://접두사로 시작 해야 합니다. 

간단한 Url에는 영숫자 문자 (a-z, A-z, 0-9, 마침표 (.)만 포함할 수 있습니다. 다른 문자를 사용 하는 경우 간단한 Url이 예상 대로 작동 하지 않을 수 있습니다.

## <a name="changing-simple-urls-after-deployment"></a>배포 후 간단한 Url 변경
<a name="BK_Valid"> </a>

초기 배포 후 간단한 URL을 변경 하는 경우에는 변경 내용이 간단한 Url에 대 한 DNS 레코드 및 인증서에 영향을 주는 방식을 알아야 합니다. 간단한 URL의 기본이 변경 되는 경우 DNS 레코드 및 인증서도 변경 해야 합니다. 예를 들어 SfB2015.contoso.com에서 https://SfB2015.contoso.com/Meet 로 https://meet.contoso.com 변경 하면 기본 URL이 MEET.CONTOSO.COM로 변경 되므로 DNS 레코드와 인증서를 변경 해야 meet.contoso.com을 참조할 수 있습니다. 간단한 URL을에서 https://SfB2015.contoso.com/Meet 으로 https://SfB2015.contoso.com/Meetings변경한 경우 SfB2015.contoso.com의 기본 url은 동일 하 게 유지 되므로 DNS 또는 인증서를 변경할 필요가 없습니다.

그러나 간단한 URL 이름을 변경할 때마다 각 디렉터 및 프런트 엔드 서버에서 **-CsComputer** 를 실행 하 여 변경 내용을 등록 해야 합니다.

## <a name="naming-examples-for-simple-urls"></a>간단한 Url에 대 한 명명 예제
<a name="BK_Valid"> </a>

간단한 Url의 이름을 지정 하는 데 권장 되는 세 가지 옵션이 있습니다. 선택 하는 옵션에 따라 간단한 Url을 지 원하는 DNS 레코드 및 인증서 설정 방법에 대 한 영향이 있습니다. 각 옵션에서 조직의 각 SIP 도메인에 대해 하나의 모임 단순 URL을 구성 해야 합니다. 

사용 중인 SIP 도메인의 수에 관계 없이 모든 조직에서 전화 접속 및 관리자 용으로 하나의 간단한 URL만 필요 합니다.

옵션 1에서 각 단순 URL에 대 한 새 SIP 도메인 이름을 만듭니다.

이 옵션을 사용 하는 경우 각 단순 URL에 대 한 별도의 DNS A 레코드가 필요 하며, 각 일치 하는 단순 URL은 인증서에 명명 되어야 합니다.

**간단한 URL 명명 옵션 1**


| **간단한 URL** <br/> | **예** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| 시켜  <br/>          | https://meet.contoso.comhttps://meet.fabrikam.com(조직의 각 SIP 도메인에 대해 하나씩)  <br/> |
| 전화 접속  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| 관리자  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

옵션 2에서는 간단한 Url이 도메인 이름 SfB2015.contoso.com를 기반으로 합니다. 따라서 세 가지 유형의 간단한 Url을 모두 사용할 수 있는 하나의 DNS A 레코드도 필요 합니다. 이 DNS A 레코드는 SfB2015.contoso.com를 참조 합니다. 또한 조직의 다른 SIP 도메인에 대 한 별도의 DNS A 레코드가 필요 합니다. 

**간단한 URL 명명 옵션 2**


| **간단한 URL** <br/> | **예** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| 시켜  <br/>          | https://SfB2015.contoso.com/Meethttps://SfB2015.fabrikam.com/Meet(조직의 각 SIP 도메인에 대해 하나씩)  <br/> |
| 전화 접속  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| 관리자  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

옵션 3은 많은 SIP 도메인이 있는 경우 각 사용자에 게 별도의 단순 Url을 사용 하도록 하 고, 이러한 간단한 Url에 대 한 DNS 레코드 및 인증서 요구 사항을 최소화 하려는 경우에 가장 유용 합니다. 

**간단한 URL 명명 옵션 3**


| **간단한 URL** <br/> | **예** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| 시켜  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| 전화 접속  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| 관리자  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>간단한 Url에 대 한 재해 복구 옵션
<a name="BK_Valid"> </a>

프런트 엔드 풀을 포함 하는 사이트가 여러 개 있고 DNS 공급자가 GeoDNS를 지 원하는 경우, 장애 복구를 지원 하도록 간단한 Url에 대 한 DNS 레코드를 설정 하 여 전체 프론트 엔드 풀 하나가 다운 되어도 간단한 URL 기능이 계속 됩니다. 이 재해 복구 기능은 모임 및 전화 접속 간단한 Url을 지원 합니다.

이를 구성 하려면 두 개의 GeoDNS 주소를 만듭니다. 각 주소에는 재해 복구용으로 서로 연결 된 두 개의 풀로 확인 되는 두 개의 DNS A 또는 CNAME 레코드가 있습니다. 하나의 GeoDNS 주소는 내부 액세스에 사용 되며, 두 풀의 내부 웹 FQDN 또는 부하 분산 장치 IP 주소로 확인 됩니다. 다른 GeoDNS 주소는 외부 액세스에 사용 되며, 두 풀의 외부 웹 FQDN 또는 부하 분산 장치 IP 주소를 확인 합니다. 다음은 풀에 대 한 Fqdn을 사용 하 여 단순 URL을 충족 하는 예제입니다. 

```
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

그런 다음 두 GeoDNS 주소에 대 한 meet.contoso.com (예:)와 일치 하는 단순 URL을 확인 하는 CNAME 레코드를 만듭니다.

> [!NOTE]
> 네트워크에서 hairpinning를 사용 하는 경우 (조직 내에서 제공 하는 트래픽을 포함 하 여 외부 링크를 통해 모든 간단한 URL 트래픽을 라우팅하는 경우), 외부 GeoDNS 주소를 구성 하 고 해당 하는 단순 URL만 문제를 해결할 수 있습니다. 외부 주소

이 메서드를 사용 하는 경우 라운드 로빈 메서드를 사용 하 여 두 개의 풀에 요청을 분산 하거나, 기본 풀 (예: 지리적으로 가까운 풀)에 연결 하 고, 다음의 경우에만 다른 풀을 사용 하도록 각 GeoDNS 주소를 구성할 수 있습니다. 연결 실패. 

전화 접속 단순 URL에 대해 동일한 구성을 설정할 수 있습니다. 이렇게 하려면 이전 예제와 같은 추가 레코드를 만들고 DNS 레코드 `dialin` `meet` 에서 대체 합니다. 관리 간단한 URL의 경우이 섹션의 앞에 나열 된 세 가지 옵션 중 하나를 사용 합니다.

이 구성을 설정한 후에는 모니터링 응용 프로그램을 사용 하 여 오류를 감시 하도록 HTTP 모니터링을 설정 해야 합니다. 외부 액세스의 경우 모니터링을 통해 HTTPS가 lyncdiscover를 얻을 수 있습니다.<sipdomain> 외부 웹 FQDN 또는 두 풀에 대 한 부하 분산 장치 IP 주소에 대 한 요청이 성공적으로 수행 되었습니다. 예를 들어 다음 요청에는 **ACCEPT** 헤더가 없어야 하 고 **200 OK**를 반환 해야 합니다.

```
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

내부 액세스의 경우 두 풀에 대 한 내부 웹 FQDN 또는 부하 분산 장치 IP 주소에서 포트 5061을 모니터링 해야 합니다. 연결 실패가 감지 되는 경우 이러한 풀의 VIP는 포트 80, 443 및 4443을 닫아야 합니다.


