<template>
  <v-app>
    <v-layout>
      <v-navigation-drawer width="200" :expand-on-hover="drawer=true" v-model="drawer" :rail="rail" permanent>
        <v-toolbar style="background-color: white;">
          <v-toolbar-title class="ma-3">
            <v-img src="https://res.cloudinary.com/dgtjdhrnq/image/upload/v1705460127/logo1_adshdl.png"></v-img>
          </v-toolbar-title>
        </v-toolbar>
        <v-divider></v-divider>
        <v-list density="compact" nav>
          <v-list-item prepend-icon="mdi-apps" title="Sản phẩm" value="Sản phẩm" to='product'></v-list-item>
          <v-list-item prepend-icon="mdi-account-group" title="User" value="User" to='user'></v-list-item>
        </v-list>
      </v-navigation-drawer>
      <v-main style="background-color: rgb(247, 247, 247);min-height: 100vh;">
        <v-app-bar class="px-4" color="rgb(247, 247, 247)" :elevation="0" rounded="0">
        <h3 class="pa-1">Danh sách sản phẩm</h3>
        <v-spacer></v-spacer>
        <v-btn>
          <v-badge content="5" color="red">
            <v-icon>mdi-bell</v-icon>
          </v-badge>
        </v-btn>
        <v-avatar>
          <v-img src="https://cdn.vuetifyjs.com/images/john.jpg" alt="John"></v-img>
        </v-avatar>
      </v-app-bar>
        <v-container>
          <v-row>
            <v-col cols="3">
              <v-text-field style="background-color: white;" density="compact" variant="outlined" label="Tìm kiếm"
                append-inner-icon="mdi mdi-magnify" single-line hide-details class="mr-2"></v-text-field>
            </v-col>
            <v-col cols="9" class="text-right">
              <v-btn @click="showDialog = true" color="primary" prepend-icon="mdi mdi-plus"
                class="text-uppercase">Thêm</v-btn>
            </v-col>
          </v-row>
          <v-row>
            <v-col cols="12">
              <v-card>
                <v-table density="compact">
                  <thead>
                    <tr>
                      <th class="text-left">
                        Tên sản phẩm
                      </th>
                      <th class="text-left">
                        Giá
                      </th>
                      <th class="text-left">
                        Số lượng
                      </th>
                      <th class="text-left">
                        Mô tả
                      </th>
                      <th class="text-left">
                        Ảnh
                      </th>
                      <th class="text-center">
                        Acction
                      </th>
                    </tr>
                  </thead>
                  <tbody>
                    <tr v-for="i in 10" :key="i">
                      <td>Sản phẩm {{ i }}</td>
                      <td>$6,000</td>
                      <td>1</td>
                      <td style="width: 250px;" class="v-text-truncate">
                        Lorem ipsum dolor sit amet
                      </td>
                      <td>
                        <v-img width="60" height="50"
                          src="https://res.cloudinary.com/dgtjdhrnq/image/upload/v1705460127/logo1_adshdl.png"></v-img>
                      </td>
                      <td class="text-center">
                        <v-btn variant="text"><v-icon>mdi-pencil</v-icon></v-btn>
                        <v-btn variant="text"><v-icon>mdi-delete</v-icon></v-btn>
                      </td>
                    </tr>
                  </tbody>
                </v-table>
                <v-row class="ma-2">
                  <v-col cols="8">
                    <v-row>
                      <p class="mt-5 opacity">Showing</p>
                      <v-col cols="2">
                        <v-select
                          density="compact"
                          :items="['10', '20', '25', '30', 'All']"
                          variant="outlined"
                        ></v-select>
                      </v-col>
                      <p class="mt-5 opacity">of 50</p>
                    </v-row>
                  </v-col>
                  <!-- <v-col cols="1" class="text-right">
                      <span style="font-size: 11px;">Showing</span>
                    </v-col>
                    <v-col cols="2">
                      <v-select style="width: 100px;height: 5px !important;"
                          density="compact"
                          :items="['10', '20', '25', '30', 'All']"
                          variant="outlined"
                        ></v-select>
                    </v-col>
                  <v-col cols="2"></v-col> -->
                  <v-col cols="4" class="text-right">
                    <v-pagination variant="text" density="compact" :length="10" ></v-pagination>
                  </v-col>
                </v-row>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-main>
      <v-dialog max-width="500px" v-model="showDialog">
        <v-card>
            <v-card-title style="font-weight: bold;"><h4>Tạo mới</h4></v-card-title>
            <v-container style="background-color: rgb(247, 247, 247);">
              <v-row>
                <v-col cols="12" style="font-size: 13px;">
                  <p>Tên sản phẩm</p>
                  <v-text-field style="background-color: white;" density="compact" single-line hide-details variant="outlined"></v-text-field>
                </v-col>
                <v-col cols="12" style="font-size: 13px;">
                  <p>Giá</p>
                  <v-text-field style="background-color: white;" density="compact" single-line hide-details variant="outlined"></v-text-field>
                </v-col>
                <v-col cols="12" style="font-size: 13px;">
                  <p>Số lượng</p>
                  <v-text-field style="background-color: white;" density="compact" single-line hide-details variant="outlined"></v-text-field>
                </v-col>
                <v-col cols="12" style="font-size: 13px;">
                  <p>Mô tả</p>
                  <v-textarea style="background-color: white;" density="compact" single-line hide-details variant="outlined"></v-textarea>
                </v-col>
                <v-col cols="12" style="font-size: 13px;">
                  <p>Ảnh sản phẩm</p>
                  <v-text-field placeholder="Nhập link ảnh" style="background-color: white;" density="compact" single-line hide-details variant="outlined"></v-text-field>
                </v-col>
              </v-row>
            </v-container>
            <v-card-actions class="pr-4">
              <v-spacer></v-spacer>
              <v-btn text="Hủy"></v-btn>
              <v-btn color="primary" variant="elevated" text="Thêm"></v-btn>
            </v-card-actions>
          </v-card>
      </v-dialog>
    </v-layout>
  </v-app>
</template>
<script>
import NavigrationDrawerVue from '@/components/NavigrationDrawer.vue'
export default {
  components: {
    NavigrationDrawerVue
  }
  ,
  data() {
    return {
      drawer: true,
      rail: true,
      showDialog: false
    }
  },
}
</script>

<style scoped>
.text-truncate {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}
.opacity{
  opacity: 0.6;
}
</style>