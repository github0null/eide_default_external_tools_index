
# eide_default_external_tools_index

在使用 eide 的 `Setup Utility Tools` 功能时，eide 通过该 `index.json` 获取可用的实用工具程序

通过在该 `index.json` 中添加项，eide 即可支持工具的下载和自动安装

---

`index.json` 接口定义：

```ts

export interface ExternalUtilToolIndexDef {

	id: string; // tool id

	name: string; // readable name

	resources: {
		// resource nodejs platform, like: win32, linux ...
		[platform: string]: {

			url: string; // zip, 7z direct download link (https), like: 'https://test.com/gcc.zip'

			zip_type: string; // '7z' or 'zip'

			bin_dir?: string; // bin dir relative path

			detail?: string; // description

			win_drv_path?: { // win32 driver exe path
				// arch: 'x86' or 'x64'
				[arch: string]: string;
			};
		}
	};
}

```
