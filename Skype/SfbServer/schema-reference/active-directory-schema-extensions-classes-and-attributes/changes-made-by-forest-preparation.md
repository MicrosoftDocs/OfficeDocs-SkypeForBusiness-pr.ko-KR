---
title: 비즈니스용 Skype 서버에서 포리스트 준비로 변경한 내용
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: 이 섹션에서는 포리스트 준비 단계를 통해 만들어지는 전역 설정과 개체, 유니버설 서비스 및 관리 그룹에 대해 설명합니다.
ms.openlocfilehash: 4e8032cb91b012c710dc509708a813d55825f7a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831918"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 포리스트 준비로 변경한 내용

이 섹션에서는 포리스트 준비 단계를 통해 만들어지는 전역 설정과 개체, 유니버설 서비스 및 관리 그룹에 대해 설명합니다.

## <a name="active-directory-global-settings-and-objects"></a>Active Directory 전역 설정 및 개체

모든 새 비즈니스용 Skype 서버 배포의 경우처럼 구성 컨테이너에 전역 설정을 저장하는 경우 포리스트 준비에서는 기존 서비스 컨테이너를 사용하고 Configuration\Services 개체 아래에 **RTC 서비스** 개체를 추가합니다. 포리스트 준비에서는 RTC Service 개체 아래에 msRTCSIP-GlobalContainer 유형의 **Global Settings** 개체를 추가합니다. 전역 설정 개체에는 비즈니스용 Skype 서버 배포에 적용되는 모든 설정이 저장됩니다. System 컨테이너에 전역 설정을 저장하는 경우 포리스트 준비에서는 루트 도메인 System 컨테이너 아래의 Microsoft 컨테이너와 System\Microsoft 개체 아래의 RTC Service 개체를 사용합니다.

또한 포리스트 준비에서는 절차가 실행되는 루트 도메인에 대한 새로운 **msRTCSIP-Domain** 개체를 추가합니다.

## <a name="active-directory-universal-service-and-administration-groups"></a>Active Directory 유니버설 서비스 및 관리 그룹

포리스트 준비에서는 지정한 도메인을 기반으로 유니버설 그룹을 만들고 이러한 그룹에 대한 ACE(액세스 제어 항목)를 추가합니다. 이 단계에서 유니버설 그룹은 지정하는 도메인의 User 컨테이너에 만들어집니다.

유니버설 그룹에서는 관리자가 전역 설정 및 서비스를 액세스하고 관리할 수 있습니다. 포리스트를 준비하면 다음 유형의 유니버설 그룹이 추가됩니다.

- **관리 그룹** 이러한 그룹은 비즈니스용 Skype 서버 네트워크에 대한 관리자 역할을 정의합니다.

- **인프라 그룹** 이러한 그룹은 비즈니스용 Skype 서버 인프라의 특정 영역에 액세스할 수 있는 권한을 제공합니다. 이 그룹은 관리 그룹의 구성 요소로 작동합니다. 이러한 그룹을 수정하거나 여기에 사용자를 직접 추가해서는 안 됩니다.

- **서비스 그룹** 이러한 그룹은 다양한 비즈니스용 Skype 서버 서비스에 액세스하는 데 필요한 서비스 계정입니다.

다음 표에서는 관리 그룹에 대해 설명합니다.

**포리스트 준비 중에 생성되는 관리 그룹**

|**관리 그룹**|**설명**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |구성원이 모든 서버 역할, 전역 설정 및 사용자를 포함하여 서버 및 풀 설정을 관리할 수 있습니다.  <br/> |
|RTCUniversalUserAdmins  <br/> |구성원이 사용자 설정을 관리하고 한 서버 또는 풀에서 다른 서버 또는 풀로 사용자를 이동할 수 있습니다.  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |구성원이 서버, 풀 및 사용자 설정을 읽을 수 있습니다.  <br/> |

다음 표에서는 인프라 그룹에 대해 설명합니다.

**포리스트 준비 중에 생성되는 인프라 그룹**

|**인프라 그룹**|**설명**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |비즈니스용 Skype 서버의 전역 설정 개체에 대한 쓰기 권한을 부여합니다.  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |비즈니스용 Skype 서버의 전역 설정 개체에 대한 읽기 전용 액세스 권한을 부여합니다.  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |비즈니스용 Skype 서버 사용자 설정에 대한 읽기 전용 액세스 권한을 부여합니다.  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |비즈니스용 Skype 서버 설정에 대한 읽기 전용 액세스 권한을 부여합니다. 이 그룹은 풀 수준 설정에는 액세스할 수 없고 개별 서버와 관련된 설정에만 액세스할 수 있습니다.  <br/> |
|RTCUniversalSBATechnicians  <br/> |비즈니스용 Skype 서버 구성에 대한 읽기 전용 액세스 권한을 부여하며 설치 중에 Survivable Branch Appliance의 Local Administrators 그룹에 배치됩니다.  <br/> |

다음 표에서는 서비스 그룹에 대해 설명합니다.

**포리스트 준비 중에 생성되는 서비스 그룹**

|**서비스 그룹**|**설명**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |프런트 엔드 서버 및 Standard Edition 서버를 실행하기 위해 사용되는 서비스 계정을 포함합니다. 이 그룹은 서버에서 비즈니스용 Skype 서버 전역 설정 및 Active Directory 사용자 개체에 대한 읽기/쓰기 액세스를 허용합니다.  <br/> |
|RTCComponentUniversalServices  <br/> |A/V 회의 서버, 웹 서비스, 중재 서버, 보관 서버 및 모니터링 서버를 실행하는 데 사용되는 서비스 계정을 포함합니다.  <br/> |
|RTCProxyUniversalServices  <br/> |비즈니스용 Skype 서버 에지 서버를 실행하기 위해 사용되는 서비스 계정을 포함합니다.  <br/> |
|RTCUniversalConfigReplicator  <br/> |비즈니스용 Skype 서버 중앙 관리 저장소 복제에 참여할 수 있는 서버를 포함합니다.  <br/> |
|RTCSBAUniversalServices  <br/> |비즈니스용 Skype 서버 설정에 대한 읽기 전용 액세스 권한을 부여하지만, Survivable Branch Server 및 Survivable Branch Appliance 배포를 구성할 수 있습니다.  <br/> |

그런 다음 포리스트 준비에서는 다음과 같이 해당 인프라 그룹에 서비스 및 관리 그룹을 추가합니다.

- RTCUniversalServerAdmins는 RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup 및 RTCUniversalUserReadOnlyGroup에 추가됩니다.

- RTCUnversalUserAdmins는 RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup 및 RTCUniversalUserReadOnlyGroup의 구성원으로 추가됩니다.

- RTCHSUniversalServices, RTCComponentUniversalServices 및 RTCUniversalReadOnlyAdmins는 RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup 및 RTCUniversalUserReadOnlyGroup의 구성원으로 추가됩니다.

또한 포리스트 준비에서는 다음과 같은 RBAC(역할 기반 액세스 제어) 그룹을 만듭니다.

- CSAdministrator

- CSArchivingAdministrator

- CSHelpDesk

- CSLocationAdministrator

- CSResponseGroupAdministrator

- CSServerAdministrator

- CSUserAdministrator

- CSViewOnlyAdministrator

- CSVoiceAdministrator

- CsPersistentChatAdministator

- CsResponseGroupManager

RBAC 역할 및 각 역할에 허용되는 작업에 대한 자세한 내용은 계획 설명서에서 [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)를 참조하십시오.

포리스트 준비에서는 개인 및 공용 ACE를 모두 만듭니다. 비즈니스용 Skype 서버에서 사용하는 전역 설정 컨테이너에 개인 AES를 만듭니다. 이 컨테이너는 비즈니스용 Skype 서버에서만 사용하며 전역 설정을 저장하는 위치에 따라 루트 도메인의 구성 컨테이너 또는 시스템 컨테이너에 있습니다. 아래 표에 포리스트 준비에서 만들어지는 공용 ACE가 나와 있습니다.

**포리스트 준비에서 만들어지는 공용 ACE**


| **ACE**                                                                 | **RTCUniversalGlobalReadOnlyGroup** |
|:------------------------------------------------------------------------|:------------------------------------|
| 루트 도메인 시스템 컨테이너 읽기(상속되지) **\\**\* <br/>        | X  <br/>                            |
| 구성의 DisplaySpecifiers 컨테이너 읽기(상속되지)  <br/> | X  <br/>                            |

> [!NOTE]
> <strong>\\</strong>*상속되지 않은 AES는 이러한 컨테이너에서 자식 개체에 대한 액세스 권한을 부여하지 않습니다. 상속된 AES는 이러한 컨테이너 아래에 있는 자식 개체에 대한 액세스 권한을 부여합니다.

구성 명명 컨텍스트 아래의 구성 컨테이너에서 포리스트 준비는 다음 작업을 수행합니다.

- 사용자, 연락처 및 InetOrgPersons에 대한 언어 표시 지정(예: CN=user-Display,CN=409,CN=DisplaySpecifiers)의 adminContextMenu 및 adminPropertyPages 특성 아래에 **RTC property** 페이지의 항목 **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** 를 추가합니다.

- **Extended-Rights** 아래에 User 및 Contact 클래스에 적용되는 **controlAccessRight** 유형의 **RTCPropertySet** 개체를 추가합니다.

- **Extended-Rights** 아래에 User, Contact, OU 및 DomainDNS 클래스에 적용되는 **controlAccessRight** 유형의 **RTCUserSearchPropertySet** 개체를 추가합니다.

- 각 언어 OU(조직 구성 단위) 표시 지정자(예: CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers)의 **extraColumns** 특성 아래에 **msRTCSIP-PrimaryUserAddress** 를 추가하고, 기본 표시(예: CN=default-Display, CN=409,CN=DisplaySpecifiers)의 **extraColumns** 특성 값을 복사합니다.

- Users, Contacts 및 InetOrgPerson 개체에 대한 각 언어 표시 지정자(예: 영어인 경우 CN=user-Display,CN=409,CN=DisplaySpecifiers)의 **attributeDisplayNames** 특성 아래에 **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** 및 **msRTCSIP-UserEnabled** 필터링 특성을 추가합니다.


