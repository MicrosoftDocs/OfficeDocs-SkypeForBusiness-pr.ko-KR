---
title: 모니터링 및 보관 메뉴의 작업에 PowerShell 사용
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
description: '요약: 비즈니스용 Skype 서버 및 보관 메뉴에 대한 Cmdlet 매핑에 대한 제어판을 제공합니다.'
ms.openlocfilehash: b286cf1ad1f52e67c4e4171402927c24908aa4ac
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626230"
---
# <a name="monitoring-and-archiving"></a>모니터링 및 보관

이 문서에서는 cmdlet을 사용하여  레거시 제어판의 모니터링 및 보관 메뉴 항목과 비슷한 결과를 얻을 수 있는 방법에 대해 설명합니다.

이 문서에서는 다음과 같은 하위 메뉴에 대해 설명합니다.

- [모니터링 및 보관](#monitoring-and-archiving)
  - [통화 세부 정보 녹음](#call-detail-recording)
  - [경험 품질 데이터](#quality-of-experience-data)
  - [보관 정책](#archiving-policy)
  - [보관 구성](#archiving-configuration)

## <a name="call-detail-recording"></a>통화 정보 기록

**통화 정보 기록** 하위 메뉴를 사용하면 관리자가 CDR(통화 정보 기록) 설정을 관리할 수 있습니다. CDR을 사용하면 피어 투 피어 인스턴트 메시징 세션, VoIP(Voice over Internet Protocol) 전화 통화 및 회의 통화 등의 사용 현황을 추적할 수 있습니다.

사용자가 통화 정보 기록에 대해 수행할 수 있는 다양한 작업을 고려해 비즈니스용 Skype 이러한 작업을 매핑합니다.

---

> **시나리오 1:** 모든 CDR 구성 나열

   ![Cdr 구성 목록](./media/cdr-configurations-1.png)

***Cmdlet***

[Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration)

***예***

```powershell
 Get-CsCdrConfiguration
```

---

> **시나리오 2:** 새 CDR 구성 만들기

   ![Cdr 구성 만들기](./media/cdr-configurations-2.png)

***Cmdlet***

[New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration)  

***예***

```powershell
 New-CsCdrConfiguration -Identity site:Redmond -EnableCDR $False
```

---

> **시나리오 3:** 선택한 CDR 구성에 대한 세부 정보 확인

   ![Cdr 구성 사용](./media/cdr-configurations-3.png)

***Cmdlet***

[Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration)

***예***

```powershell
 Get-CsCdrConfiguration -Identity site:Redmond
```

---

> **시나리오 4:** 선택한 CDR 구성 삭제

   ![Cdr 구성 삭제](./media/cdr-configurations-4.png)

***Cmdlet***

[Remove-CsCdrConfiguration](/powershell/module/skype/remove-cscdrconfiguration)

***예***

```powershell
 Remove-CsCdrConfiguration -Identity site:Redmond
```

---

> **시나리오 5:** CDR 구성 업데이트

   ![Cdr 구성 업데이트](./media/cdr-configurations-5.png)

***Cmdlet***

[Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration)

***예***

```powershell
 Set-CsCdrConfiguration -Identity site:Redmond -PurgeHourOfDay 23
```

---

## <a name="quality-of-experience-data"></a>경험 품질 데이터

QoE(QUALITY **OF EXPERIENCE DATA)** 하위 메뉴를 사용하면 관리자가 QoE(QoE) 설정을 관리할 수 있습니다. 조직 전체에서 여기에는 그룹 확장, 인증서 설정 및 허용되는 인증 방법 관리가 포함됩니다. 관리자는 전역, 사이트 및 서비스 범위에서 서로 다른 설정을 구성할 수 있기 때문에(웹 서비스 서비스만 해당) 서로 다른 사용자 및 위치에 대해 웹 서비스 기능을 사용자 지정할 수 있습니다.

사용자가 웹 서비스 및 웹 서비스에서 수행할 수 있는 다양한 작업을 비즈니스용 Skype cmdlet에 매핑합니다. 

---
> **시나리오 1:** 모든 QoE 구성 나열

   ![QoE 구성 목록](./media/qoe-configuration-1.png)

***Cmdlet***

[Get-CsQoEConfiguration](/powershell/module/skype/get-csqoeconfiguration)

***예***

```powershell
 Get-CsQoEConfiguration
```

---

> **시나리오 2:** 새 QoE 구성 만들기

   ![새 QoE 구성](./media/qoe-configuration-2.png)

***Cmdlet***

[New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration)  

***예***

```powershell
 New-CsQoEConfiguration -Identity site:Redmond -EnableQoE $False
```

---

> **시나리오 3:** 선택한 QoE 구성에 대한 세부 정보 확인

   ![QoE 구성 확인](./media/qoe-configuration-3.png)

***Cmdlet***

[Get-CsQoEConfiguration](/powershell/module/skype/get-csqoeconfiguration)

***예***

```powershell
 Get-CsQoEConfiguration -Identity site:Redmond
```

---

> **시나리오 4:** 선택한 QoE 구성 삭제

   ![QoE 구성 삭제](./media/qoe-configuration-4.png)

***Cmdlet***

[Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration)

***예***

```powershell
 Remove-CsQoEConfiguration -Identity site:Redmond
```

---

> **시나리오 5:** QoE 구성 업데이트

   ![QoE 구성 업데이트](./media/qoe-configuration-5.png)

***Cmdlet***

[Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration)

***예***

```powershell
 Set-CsQoEConfiguration -Identity site:Redmond -EnableQoE $False
```

---

## <a name="archiving-policy"></a>보관 정책

관리자는 보관 **정책을** 사용하여 IM(인스턴트 메시징) 세션 보관 정책을 관리할 수 있습니다. 보관 정책을 사용하면 내부 사용자 간에 또는 내부 사용자와 외부 사용자 간에 진행하는 모든 IM 및 웹 회의 세션을 보관할 수 있습니다.

사용자가 **ARCHIVING POLICY에서** 수행할 수 있는 다양한 작업을 고려해 비즈니스용 Skype 이러한 작업을 매핑합니다.

---

> **시나리오 1:** 모든 보관 정책 나열

   ![목록 보관 정책](./media/archiving-policy-1.png)

***Cmdlet***

[Get-CsArchivingPolicy](/powershell/module/skype/get-csarchivingpolicy)

***예***

```powershell
 Get-CsArchivingPolicy
```

---

> **시나리오 2:** 새 보관 정책 만들기

   ![보관 정책 만들기](./media/archiving-policy-2.png)

***Cmdlet***

[New-CsArchivingPolicy](/powershell/module/skype/new-csarchivingpolicy)  

***예***

```powershell
 New-CsArchivingPolicy -Identity site:Redmond -ArchiveInternal $True
```

---

> **시나리오 3:** 선택한 보관 정책에 대한 세부 정보 확인

   ![보관 정책 얻기](./media/archiving-policy-3.png)

***Cmdlet***

[Get-CsArchivingPolicy](/powershell/module/skype/get-csarchivingpolicy)

***예***

```powershell
 Get-CsArchivingPolicy -Identity site:Redmond
```

---

> **시나리오 4:** 선택한 보관 정책 삭제

   ![보관 정책 삭제](./media/archiving-policy-4.png)

***Cmdlet***

[Remove-CsArchivingPolicy](/powershell/module/skype/remove-csarchivingpolicy)

***예***

```powershell
 Remove-CsArchivingPolicy -Identity site:Redmond
```

---

> **시나리오 5:** 보관 정책 업데이트

   ![보관 정책 업데이트](./media/archiving-policy-5.png)

***Cmdlet***

[Set-CsArchivingPolicy](/powershell/module/skype/set-csarchivingpolicy)

***예***

```powershell
 Set-CsArchivingPolicy -Identity global -ArchiveInternal $True
```

---

## <a name="archiving-configuration"></a>보관 구성

관리자는 **ARCHIVING 구성을** 사용하여 조직에서 IM(인스턴트 메시징) 세션을 보관하는 방법 또는 보관할지 구성할 수 있습니다.

사용자가 보관 구성에 대해 수행할 수 있는 다양한 작업을 고려해 비즈니스용 Skype 매핑할 수 있습니다.

---

> **시나리오 1:** 모든 보관 구성 나열

   ![목록 보관 구성](./media/archiving-configuration-1.png)

***Cmdlet***

[Get-CsArchivingConfiguration](/powershell/module/skype/get-csarchivingconfiguration)

***예***

```powershell
 Get-CsArchivingConfiguration
```

---

> **시나리오 2:** 새 보관 구성 만들기

   ![보관 구성 만들기](./media/archiving-configuration-2.png)

***Cmdlet***

[New-CsArchivingConfiguration](/powershell/module/skype/new-csarchivingconfiguration)  

***예***

```powershell
 New-CsArchivingConfiguration -Identity site:Redmond -EnableArchiving "ImOnly"
```

---

> **시나리오 3:** 선택한 보관 구성에 대한 세부 정보 확인

   ![보관 구성 확인](./media/archiving-configuration-3.png)

***Cmdlet***

[Get-CsArchivingConfiguration](/powershell/module/skype/get-csarchivingconfiguration)

***예***

```powershell
 Get-CsArchivingConfiguration -Identity site:Redmond
```

---

> **시나리오 4:** 선택한 보관 구성 삭제

   ![보관 구성 삭제](./media/archiving-configuration-4.png)

***Cmdlet***

[Remove-CsArchivingConfiguration](/powershell/module/skype/remove-csarchivingconfiguration)

***예***

```powershell
 Remove-CsArchivingConfiguration -Identity site:Redmond
```

---

> **시나리오 5:** 보관 구성 업데이트

   ![보관 구성 업데이트](./media/archiving-configuration-5.png)

***Cmdlet***

[Set-CsArchivingConfiguration](/powershell/module/skype/set-csarchivingconfiguration)

***예***

```powershell
 Set-CsArchivingConfiguration -Identity site:Redmond -ArchiveDuplicateMessages $False -KeepArchivingDataForDays 30
```

---
