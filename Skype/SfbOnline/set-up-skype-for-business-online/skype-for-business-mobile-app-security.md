---
title: 비즈니스용 Skype 모바일 앱 보안
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: '사용자에 대한 모바일 앱 보안을 설정하는 방법을 배워야 합니다. '
ms.openlocfilehash: f600230574b8d16a0f7907b4484da8ffcca6124e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239635"
---
# <a name="skype-for-business-mobile-app-security"></a><span data-ttu-id="22b9c-103">비즈니스용 Skype 모바일 앱 보안</span><span class="sxs-lookup"><span data-stu-id="22b9c-103">Skype for Business mobile app security</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

## <a name="skype-for-business-client-security"></a><span data-ttu-id="22b9c-104">비즈니스용 Skype 클라이언트 보안</span><span class="sxs-lookup"><span data-stu-id="22b9c-104">Skype for Business Client Security</span></span>

<span data-ttu-id="22b9c-105">이 문서에서는 Mobile Apps의 데이터 비즈니스용 Skype 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22b9c-105">This article covers data encryption information on Skype for Business Mobile Apps.</span></span>
  
|||||
|:-----|:-----|:-----|:-----|
||<span data-ttu-id="22b9c-106">**사용자 이름/암호**</span><span class="sxs-lookup"><span data-stu-id="22b9c-106">**Username/Password**</span></span> <br/> |<span data-ttu-id="22b9c-107">**앱 데이터(대화, 연락처 <br/> 목록, 모임)**</span><span class="sxs-lookup"><span data-stu-id="22b9c-107">**App Data (Conversations,<br/> Contact List, Meetings)**</span></span> <br/> |<span data-ttu-id="22b9c-108">**진단 로그**</span><span class="sxs-lookup"><span data-stu-id="22b9c-108">**Diagnostic logs**</span></span> <br/> |
|<span data-ttu-id="22b9c-109">**Android**</span><span class="sxs-lookup"><span data-stu-id="22b9c-109">**Android**</span></span> <br/> |<span data-ttu-id="22b9c-110">Android 계정에 자격 증명 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="22b9c-110">We store credentials information in Android Accounts.</span></span> <span data-ttu-id="22b9c-111">또한 계정으로 저장하기 전에 자격 증명을 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="22b9c-111">We also encrypt credentials before saving them into Accounts.</span></span> <span data-ttu-id="22b9c-112">암호화를 위해 **"AES/CBC/PKCS5Padding"** 알고리즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="22b9c-112">We use " **AES/CBC/PKCS5Padding** " algorithm for encryption.</span></span> <br/> |<span data-ttu-id="22b9c-113">sqlcipher라는 라이브러리를 사용하여 SQL 데이터베이스에 [저장합니다.](https://www.zetetic.net/sqlcipher/design/)</span><span class="sxs-lookup"><span data-stu-id="22b9c-113">We store in an encrypted SQL database using a library called [sqlcipher](https://www.zetetic.net/sqlcipher/design/).</span></span> <span data-ttu-id="22b9c-114">CBC 모드에서 256비트 AES의 기본 알고리즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="22b9c-114">We use their default algorithm of 256-bit AES in CBC mode.</span></span> <span data-ttu-id="22b9c-115">미사일 데이터는 항상 데이터베이스 파일에서 암호화되며 앱의 휘발성 메모리 및 호출 스택 내부에서만 암호화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22b9c-115">The data at rest is always encrypted in the database file and is only unencrypted in transit inside of the app's volatile memory and call stacks.</span></span> <span data-ttu-id="22b9c-116">또한 사용자의 이름 및 암호 암호화와 동일한 방법을 사용하여 음성 메시지 파일을 암호화합니다(DB에 저장되지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="22b9c-116">We also encrypt voicemail files using the same method as the user's name and password encryption (they are not stored in the DB).</span></span> <span data-ttu-id="22b9c-117">음성메일은 재생을 허용하기 위해 디스크에서 일시적으로 암호화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22b9c-117">Voicemails are temporarily unencrypted on disk to allow playback.</span></span>  <br/> |<span data-ttu-id="22b9c-118">이 정보는 암호화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22b9c-118">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="22b9c-119">**iOS**</span><span class="sxs-lookup"><span data-stu-id="22b9c-119">**iOS**</span></span> <br/> |<span data-ttu-id="22b9c-120">키체인에서 사용자 이름/암호를 암호화하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22b9c-120">We DO NOT encrypt the username/password in the keychain.</span></span> <span data-ttu-id="22b9c-121">그러나 키체인은 자체로 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="22b9c-121">The keychain is encrypted, however, on its own.</span></span>  <br/> |<span data-ttu-id="22b9c-122">앱 저장소의 모든 파일에 [대한 NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) 데이터 보호 플래그를 이미 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22b9c-122">We are already using [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) data protection flag on all files in the app storage.</span></span> <span data-ttu-id="22b9c-123">즉, 사용자가 디바이스를 다시 부트한 후 처음으로 디바이스 잠금을 해제할 때까지 앱 저장소의 파일이 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="22b9c-123">This means that files in the app storage would be encrypted until user unlocks the device for the very first time after the device reboot.</span></span> <br/> |<span data-ttu-id="22b9c-124">이 정보는 암호화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22b9c-124">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="22b9c-125">**Windows Phone**</span><span class="sxs-lookup"><span data-stu-id="22b9c-125">**Windows Phone**</span></span> <br/> |<span data-ttu-id="22b9c-126">Windows Phone DPAPI(데이터 보호 API)를 사용하여 Windows 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="22b9c-126">Windows Phone uses the DPAPI (Data Protection API) in Windows to secure passwords.</span></span> <span data-ttu-id="22b9c-127">사용된 암호화 체계가 AES인 것으로 생각됩니다.</span><span class="sxs-lookup"><span data-stu-id="22b9c-127">I believe the encryption scheme used is AES.</span></span> <span data-ttu-id="22b9c-128">Windows 키 크기(또는 구성표)를 구성할 수 있는 옵션이 제공되지 않습니다. 따라서 DPAPI가 제공하는 모든 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="22b9c-128">Windows doesn't give us an option to configure the key size (or scheme), so it's whatever DPAPI gives.</span></span> <span data-ttu-id="22b9c-129">디바이스 TPM을 사용하여 사용자 및 디바이스에 특정한 키를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="22b9c-129">It will use the device TPM to secure keys which are specific to the user and device.</span></span> <span data-ttu-id="22b9c-130">DPAPI 키는 앱에 국한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22b9c-130">Note that DPAPI keys are not specific to the app.</span></span>  <br/> |<span data-ttu-id="22b9c-131">WP App Data는 creds와 같이 [DPAP](/previous-versions/windows/apps/hh487164(v=vs.105))I로 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="22b9c-131">WP App Data is protected with [DPAP](/previous-versions/windows/apps/hh487164(v=vs.105))I, like the creds.</span></span> <span data-ttu-id="22b9c-132">원하는 세부 정보에 따라 앱 데이터에 대한 인덱스 정보 중 일부는 (DPAPI가 아닌) AES 암호화에 의해 보호되어 염해를 방지할 수 있으므로 암호 해독 없이 검색할 수 있으며 해당 키는 DPAPI로 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="22b9c-132">Depending on how much detail we want, some of the index information for the App Data is protected by (non-DPAPI) AES encryption to avoid salting, so we can look up without decrypting, and that key is in turn protected with DPAPI.</span></span> <span data-ttu-id="22b9c-133">캐시된 데이터는 데이터 폴더에 도달할 수 있는 경우 동일한 휴대폰의 모든 프로세스에서 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22b9c-133">Cached data can be read by any process from the same phone, assuming it can reach our data folder.</span></span> <span data-ttu-id="22b9c-134">Windows 암호화는 샌드박스 위반으로부터 보호되지 않습니다. 외부 액세스 시도만 합니다.</span><span class="sxs-lookup"><span data-stu-id="22b9c-134">Windows encryption does not protect from sandbox breach, only external access attempts.</span></span>  <br/> |<span data-ttu-id="22b9c-135">이 정보는 암호화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22b9c-135">This information is not encrypted.</span></span>  <br/> |
   
<span data-ttu-id="22b9c-136">**참고:** 위의 각 [모바일](/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) 플랫폼에서 사용할 수 있는 디바이스 핀 적용에 대한 이 공용 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22b9c-136">**Note:** Please refer to [this public documentation](/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) for device pin enforcement available on each of the above Mobile platforms</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="22b9c-137">관련 항목</span><span class="sxs-lookup"><span data-stu-id="22b9c-137">Related topics</span></span>
[<span data-ttu-id="22b9c-138">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="22b9c-138">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="22b9c-139">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="22b9c-139">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
