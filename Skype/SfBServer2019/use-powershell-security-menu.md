---
title: 보안 메뉴의 작업에 PowerShell 사용
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: '요약: 비즈니스용 Skype 서버 메뉴에 대한 Cmdlet 매핑에 대한 제어판을 제공합니다.'
ms.openlocfilehash: 6e726b13b9428b213011126abf5ac0869e6cfbf8
ms.sourcegitcommit: eba9fc680233e9e03773a2942f22afe6247eec41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60824935"
---
# <a name="security"></a>보안

이 문서에서는 cmdlet을 사용하여  레거시 제어판의 보안 메뉴 항목과 비슷한 결과를 얻을 수 있는 방법에 대해 설명합니다.

이 문서에서는 다음과 같은 하위 메뉴에 대해 설명합니다.

- [보안](#security)
  - [등록자](#registrar)
  - [웹 서비스](#web-service)
  - [PIN 정책](#pin-policy)

## <a name="registrar"></a>등록자

**REGISTRAR** 하위 메뉴를 사용하면 관리자가 프록시 서버 구성 설정을 통해 프록시 서버를 관리할 수 있습니다. 이러한 설정은 전역 범위와 서비스 범위(에지 서버 및 등록자 서비스에만 해당)에서 모두 적용할 수 있으며 클라이언트 끝점에서 사용할 수 있는 인증 프로토콜과 들어오는 프록시 서버 연결에 압축을 사용할지 여부 등의 제어를 가능하게 합니다.

등록자 에서 사용자가 수행할 수 있는 다양한 작업을 고려해 비즈니스용 Skype 이러한 작업을 매핑합니다.

---

> **시나리오 1:** 모든 프록시 구성 나열

   ![목록 프록시 구성](./media/proxy-configurations-1.png)

***Cmdlet***

[Get-CsProxyConfiguration](/powershell/module/skype/get-csproxyconfiguration)

***예***

```powershell
 Get-CsProxyConfiguration
```

---

> **시나리오 2:** 새 프록시 구성 만들기

   ![프록시 구성 만들기](./media/proxy-configurations-2.png)

***Cmdlet***

[New-CsProxyConfiguration](/powershell/module/skype/new-csproxyconfiguration)  

***예***

```powershell
 New-CsProxyConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -RequestServerCompression $True -MaxClientMessageBodySizeKb 256
```

---

> **시나리오 3:** 선택한 프록시 구성에 대한 세부 정보 확인

   ![프록시 구성 확인](./media/proxy-configurations-3.png)

***Cmdlet***

[Get-CsProxyConfiguration](/powershell/module/skype/get-csproxyconfiguration)

***예***

```powershell
 Get-CsProxyConfiguration -Identity "service:EdgeServer:atl-cs-001.litwareinc.com"
```

---

> **시나리오 4:** 선택한 프록시 구성 삭제

   ![프록시 구성 삭제](./media/proxy-configurations-4.png)

***Cmdlet***

[Remove-CsProxyConfiguration](/powershell/module/skype/remove-csproxyconfiguration)

***예***

```powershell
 Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
```

---

> **시나리오 5:** 프록시 구성 업데이트

   ![프록시 구성 업데이트](./media/proxy-configurations-5.png)

***Cmdlet***

[Set-CsProxyConfiguration](/powershell/module/skype/set-csproxyconfiguration)

***예***

```powershell
 Set-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-001.litwareinc.com -AcceptServerCompression $True
```

---

## <a name="web-service"></a>웹 서비스

보안의 **웹 서비스** 하위 메뉴 **항목을** 사용하면 관리자가 조직 전체에서 웹 서비스 구성 설정을 관리할 수 있습니다. 여기에는 그룹 확장, 인증서 설정 및 허용되는 인증 방법 관리가 포함됩니다. 관리자는 전역, 사이트 및 서비스 범위에서 서로 다른 설정을 구성할 수 있기 때문에(웹 서비스 서비스만 해당) 서로 다른 사용자 및 위치에 대해 웹 서비스 기능을 사용자 지정할 수 있습니다.

사용자가 웹 서비스 및 웹 서비스에서 수행할 수 있는 다양한 작업을 비즈니스용 Skype cmdlet에 매핑합니다. 

---
> **시나리오 1:** 모든 웹 서비스 구성 나열

   ![목록 웹 서비스 구성](./media/web-service-1.png)

***Cmdlet***

[Get-CsWebServiceConfiguration](/powershell/module/skype/get-cswebserviceconfiguration)

***예***

```powershell
 Get-CsWebServiceConfiguration
```

---

> **시나리오 2:** 새 웹 서비스 구성 만들기

   ![새 웹 서비스 구성](./media/web-service-2.png)

***Cmdlet***

[New-CsWebServiceConfiguration](/powershell/module/skype/new-cswebserviceconfiguration)  

***예***

```powershell
 New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True
```

---

> **시나리오 3:** 선택한 웹 서비스 구성에 대한 세부 정보 확인

   ![웹 서비스 구성 확인](./media/web-service-3.png)

***Cmdlet***

[Get-CsWebServiceConfiguration](/powershell/module/skype/get-cswebserviceconfiguration)

***예***

```powershell
 Get-CsWebServiceConfiguration -Identity site:Redmond
```

---

> **시나리오 4:** 선택한 웹 서비스 구성 삭제

   ![웹 서비스 구성 삭제](./media/web-service-4.png)

***Cmdlet***

[Remove-CsWebServiceConfiguration](/powershell/module/skype/remove-cswebserviceconfiguration)

***예***

```powershell
 Remove-CsWebServiceConfiguration -Identity site:Redmond
```

---

> **시나리오 5:** 웹 서비스 구성 업데이트

   ![웹 서비스 구성 업데이트](./media/Web-service-5.png)

***Cmdlet***

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration)

***예***

```powershell
 Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True
```

---

## <a name="pin-policy"></a>PIN 정책

관리자는 PIN **정책을** 사용하여 PIN 인증 속성을 관리할 수 있습니다. 예를 들어 PIN의 최소 길이를 지정하고 연속되는 숫자와 같은 "공통 패턴"을 사용하는 PIN을 허용할지 여부를 결정할 수 123456

사용자가 **PIN** 정책에 대해 수행할 수 있는 다양한 작업을 고려하고 이러한 비즈니스용 Skype 매핑할 수 있습니다.

---

> **시나리오 1:** 모든 PIN 정책 나열

   ![목록 고정 정책](./media/pin-policy-1.png)

***Cmdlet***

[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy)

***예***

```powershell
 Get-CsPinPolicy
```

---

> **시나리오 2:** 새 PIN 정책 만들기

   ![고정 정책 만들기](./media/pin-policy-2.png)

***Cmdlet***

[New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy)  

***예***

```powershell
 New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 10
```

---

> **시나리오 3:** 선택한 PIN 정책에 대한 세부 정보 확인

   ![PIN 정책 얻기](./media/pin-policy-3.png)

***Cmdlet***

[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy)

***예***

```powershell
 Get-CsPinPolicy -Identity "site:Redmond"
```

---

> **시나리오 4:** 선택한 PIN 정책 삭제

   ![PIN 정책 삭제](./media/pin-policy-4.png)

***Cmdlet***

[Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy)

***예***

```powershell
 Remove-CsPinPolicy -Identity RedmondUsersPinPolicy
```

---

> **시나리오 5:** PIN 정책 업데이트

   ![PIN 정책 업데이트](./media/pin-policy-5.png)

***Cmdlet***

[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy)

***예***

```powershell
 Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

---
