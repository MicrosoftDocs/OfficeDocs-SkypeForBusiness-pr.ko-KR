---
title: 'Lync Server 2013: 공용 공급자용 미디어 암호화 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media encryption for public providers
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205149(v=OCS.15)
ms:contentKeyID: 48185036
ms.date: 12/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 270035730b8268c56b1730d8c212e90c8a9f1a30
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40985272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a>Lync Server 2013에서 공용 공급자용 미디어 암호화 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-12-12_

Windows Live Messenger를 사용 하 여 오디오/비디오 (A/V) 페더레이션을 구현 하는 경우 다음 두 가지 매개 변수를 수정 해야 합니다. Lync Server 암호화 수준 및 EnablePublicCloudAccess 정책. 기본적으로 암호화 수준은 필수로 설정 됩니다. 이 설정을 지원으로 변경 해야 합니다. EnablePublicCloudAccess 정책이 false로 설정 된 경우이를 **True**로 설정 해야 합니다. Lync Server 관리 셸에서이 작업을 수행할 수 있습니다.

<div>

## <a name="configure-federation-for-windows-live"></a>Windows Live에 대 한 페더레이션 구성

1.  프런트 엔드 서버에서 Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server management shell**을 클릭 합니다.

2.  명령 프롬프트에서 다음 명령을 입력 합니다.
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > 이 단계는 Windows Live Messenger가 오디오/비디오의 암호화를 지원 하지 않기 때문에 필요 합니다. 이 명령은 오디오/비디오 데이터를 암호화 하도록 요구 하는 대신 글로벌 정책을 지원 암호화 설정으로 설정 합니다. 암호화를 지 원하는 클라이언트는 계속 해 서 Lync 2013와 같은 암호화를 사용 합니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

