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
description: '사용자를 위해 모바일 앱 보안을 설정 하는 방법을 알아봅니다. '
ms.openlocfilehash: 2c22f384196f0f05ca89d6f0e07ae84a1548d78a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010781"
---
# <a name="skype-for-business-mobile-app-security"></a><span data-ttu-id="7d2be-103">비즈니스용 Skype 모바일 앱 보안</span><span class="sxs-lookup"><span data-stu-id="7d2be-103">Skype for Business mobile app security</span></span>

## <a name="skype-for-business-client-security"></a><span data-ttu-id="7d2be-104">비즈니스용 Skype 클라이언트 보안</span><span class="sxs-lookup"><span data-stu-id="7d2be-104">Skype for Business Client Security</span></span>

<span data-ttu-id="7d2be-105">이 문서에서는 비즈니스용 Skype 모바일 앱의 데이터 암호화 정보에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2be-105">This article covers data encryption information on Skype for Business Mobile Apps.</span></span>
  
|||||
|:-----|:-----|:-----|:-----|
||<span data-ttu-id="7d2be-106">**사용자 이름/비밀 번호**</span><span class="sxs-lookup"><span data-stu-id="7d2be-106">**Username/Password**</span></span> <br/> |<span data-ttu-id="7d2be-107">**앱 데이터 (대화,<br/> 연락처 목록, 모임)**</span><span class="sxs-lookup"><span data-stu-id="7d2be-107">**App Data (Conversations,<br/> Contact List, Meetings)**</span></span> <br/> |<span data-ttu-id="7d2be-108">**진단 로그**</span><span class="sxs-lookup"><span data-stu-id="7d2be-108">**Diagnostic logs**</span></span> <br/> |
|<span data-ttu-id="7d2be-109">**Android**</span><span class="sxs-lookup"><span data-stu-id="7d2be-109">**Android**</span></span> <br/> |<span data-ttu-id="7d2be-110">Android 계정에 자격 증명 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2be-110">We store credentials information in Android Accounts.</span></span> <span data-ttu-id="7d2be-111">또한 자격 증명을 계정에 저장 하기 전에 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2be-111">We also encrypt credentials before saving them into Accounts.</span></span> <span data-ttu-id="7d2be-112">암호화에 " **AES/cbc-mac/PKCS5Padding** " 알고리즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2be-112">We use " **AES/CBC/PKCS5Padding** " algorithm for encryption.</span></span> <br/> |<span data-ttu-id="7d2be-113">[Sqlcipher](https://www.zetetic.net/sqlcipher/design/)라는 라이브러리를 사용 하 여 암호화 된 SQL 데이터베이스에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2be-113">We store in an encrypted SQL database using a library called [sqlcipher](https://www.zetetic.net/sqlcipher/design/).</span></span> <span data-ttu-id="7d2be-114">CBC 모드에서 기본 알고리즘의 256 비트 AES를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2be-114">We use their default algorithm of 256-bit AES in CBC mode.</span></span> <span data-ttu-id="7d2be-115">Rest의 데이터는 항상 데이터베이스 파일에서 암호화 되며 앱의 휘발성 메모리와 호출 스택 내부에서는 암호화 되지 않은 상태로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d2be-115">The data at rest is always encrypted in the database file and is only unencrypted in transit inside of the app's volatile memory and call stacks.</span></span> <span data-ttu-id="7d2be-116">또한 사용자의 이름 및 암호 암호화와 같은 방법을 사용 하 여 보이스 메일 파일을 암호화 합니다 (DB에 저장 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="7d2be-116">We also encrypt voicemail files using the same method as the user's name and password encryption (they are not stored in the DB).</span></span> <span data-ttu-id="7d2be-117">보이스 메일는 디스크에서 일시적으로 암호화 되지 않아 재생을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2be-117">Voicemails are temporarily unencrypted on disk to allow playback.</span></span>  <br/> |<span data-ttu-id="7d2be-118">이 정보는 암호화 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2be-118">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="7d2be-119">**iOS**</span><span class="sxs-lookup"><span data-stu-id="7d2be-119">**iOS**</span></span> <br/> |<span data-ttu-id="7d2be-120">키 집합의 사용자 이름/암호는 암호화 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2be-120">We DO NOT encrypt the username/password in the keychain.</span></span> <span data-ttu-id="7d2be-121">그러나 키 집합이 암호화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d2be-121">The keychain is encrypted, however, on its own.</span></span>  <br/> |<span data-ttu-id="7d2be-122">앱 저장소의 모든 파일에 대해 [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) data protection 플래그를 이미 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="7d2be-122">We are already using [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) data protection flag on all files in the app storage.</span></span> <span data-ttu-id="7d2be-123">즉, 장치를 다시 부팅 한 후 사용자가 처음으로 장치를 잠금 해제할 때까지 앱 저장소의 파일이 암호화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d2be-123">This means that files in the app storage would be encrypted until user unlocks the device for the very first time after the device reboot.</span></span> <br/> |<span data-ttu-id="7d2be-124">이 정보는 암호화 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2be-124">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="7d2be-125">**Windows Phone**</span><span class="sxs-lookup"><span data-stu-id="7d2be-125">**Windows Phone**</span></span> <br/> |<span data-ttu-id="7d2be-126">Windows Phone은 Windows에서 DPAPI (Data Protection API)를 사용 하 여 암호를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2be-126">Windows Phone uses the DPAPI (Data Protection API) in Windows to secure passwords.</span></span> <span data-ttu-id="7d2be-127">사용 된 암호화 체계가 AES 라고 생각 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2be-127">I believe the encryption scheme used is AES.</span></span> <span data-ttu-id="7d2be-128">Windows는 키 크기 (또는 구성표)를 구성 하는 옵션을 제공 하지 않으므로 DPAPI가 제공 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7d2be-128">Windows doesn't give us an option to configure the key size (or scheme), so it's whatever DPAPI gives.</span></span> <span data-ttu-id="7d2be-129">장치 TPM을 사용 하 여 사용자 및 디바이스와 관련 된 키를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2be-129">It will use the device TPM to secure keys which are specific to the user and device.</span></span> <span data-ttu-id="7d2be-130">DPAPI 키가 앱과 관련이 없다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="7d2be-130">Note that DPAPI keys are not specific to the app.</span></span>  <br/> |<span data-ttu-id="7d2be-131">WP 앱 데이터는 자격 증명 등의 [Dpap](https://msdn.microsoft.com/library/windows/apps/hh487164%28v=vs.105%29.aspx)I로 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d2be-131">WP App Data is protected with [DPAP](https://msdn.microsoft.com/library/windows/apps/hh487164%28v=vs.105%29.aspx)I, like the creds.</span></span> <span data-ttu-id="7d2be-132">사용할 세부 정보에 따라 앱 데이터에 대 한 일부 인덱스 정보는 솔트을 방지 하기 위해 (DPAPI가 아닌) AES 암호화로 보호 되므로 암호를 해독 하지 않고 조회할 수 있으며 해당 키가 DPAPI로 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d2be-132">Depending on how much detail we want, some of the index information for the App Data is protected by (non-DPAPI) AES encryption to avoid salting, so we can look up without decrypting, and that key is in turn protected with DPAPI.</span></span> <span data-ttu-id="7d2be-133">데이터 폴더에 도달할 수 있다고 가정 하 여 동일한 전화의 모든 프로세스가 캐시 된 데이터를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2be-133">Cached data can be read by any process from the same phone, assuming it can reach our data folder.</span></span> <span data-ttu-id="7d2be-134">Windows 암호화는 샌드박스 위반, 외부 액세스 시도만 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2be-134">Windows encryption does not protect from sandbox breach, only external access attempts.</span></span>  <br/> |<span data-ttu-id="7d2be-135">이 정보는 암호화 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2be-135">This information is not encrypted.</span></span>  <br/> |
   
<span data-ttu-id="7d2be-136">**참고:** 위의 각 모바일 플랫폼에서 사용할 수 있는 장치 pin 적용에 대 한 [이 공개 문서](https://docs.microsoft.com/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7d2be-136">**Note:** Please refer to [this public documentation](https://docs.microsoft.com/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) for device pin enforcement available on each of the above Mobile platforms</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7d2be-137">관련 주제</span><span class="sxs-lookup"><span data-stu-id="7d2be-137">Related topics</span></span>
[<span data-ttu-id="7d2be-138">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="7d2be-138">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="7d2be-139">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="7d2be-139">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
