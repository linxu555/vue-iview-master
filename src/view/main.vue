<style scoped>
  .layout{
    border: 1px solid #d7dde4;
    background: #f5f7f9;
    position: relative;
    border-radius: 4px;
    overflow: hidden;
  }
  .layout-logo{
    width: 100px;
    height: 30px;
    background: #5b6270;
    border-radius: 3px;
    float: left;
    position: relative;
    top: 15px;
    left: 20px;
  }
  .layout-nav{
    width: 420px;
    margin: 0 auto;
    margin-right: 20px;
  }
  .layout-footer-center{
    text-align: center;
  }
</style>
<template>
    <div class="main">
        <div class="layout">
          <Layout>
            <Header>
              <Menu mode="horizontal" theme="dark" active-name="1">
                <div class="layout-logo"></div>
                <div class="layout-nav">
                  <MenuItem name="1">
                    <Icon type="ios-navigate"></Icon>
                    Item 1
                  </MenuItem>
                  <MenuItem name="2">
                    <Icon type="ios-keypad"></Icon>
                    Item 2
                  </MenuItem>
                  <MenuItem name="3">
                    <Icon type="ios-analytics"></Icon>
                    Item 3
                  </MenuItem>
                  <MenuItem name="4">
                    <Icon type="ios-paper"></Icon>
                    Item 4
                  </MenuItem>
                </div>
              </Menu>
            </Header>
            <Layout :style="{padding: '0 50px'}">
              <Breadcrumb :style="{margin: '16px 0'}">
                <BreadcrumbItem>Home</BreadcrumbItem>
                <BreadcrumbItem>Components</BreadcrumbItem>
                <BreadcrumbItem>Layout</BreadcrumbItem>
              </Breadcrumb>
              <Content :style="{padding: '24px 0', minHeight: '280px', background: '#fff'}">
                <Layout>
                  <Sider hide-trigger :style="{background: '#fff'}">
                    <Menu active-name="1-2" theme="light" width="auto" :open-names="['1']">
                      <Submenu name="1">
                        <template slot="title">
                          <Icon type="ios-navigate"></Icon>
                          数据库1
                        </template>
                        <MenuItem name="1-1">table 1</MenuItem>
                        <MenuItem name="1-2">table 2</MenuItem>
                        <MenuItem name="1-3">table 3</MenuItem>
                      </Submenu>
                      <Submenu name="2">
                        <template slot="title">
                          <Icon type="ios-navigate"></Icon>
                          数据库2
                        </template>
                        <MenuItem name="1-1">table 1</MenuItem>
                        <MenuItem name="1-2">table 2</MenuItem>
                        <MenuItem name="1-3">table 3</MenuItem>
                      </Submenu>
                      <Submenu name="3">
                        <template slot="title">
                          <Icon type="ios-navigate"></Icon>
                          数据库3
                        </template>
                        <MenuItem name="1-1">table 1</MenuItem>
                        <MenuItem name="1-2">table 2</MenuItem>
                        <MenuItem name="1-3">table 3</MenuItem>
                      </Submenu>
                    </Menu>
                  </Sider>
                  <Content :style="{padding: '24px', minHeight: '280px', background: '#fff'}">
                   <!-- <div class="list">-->
                      <Card shadow>

                        <h3  style="font-family:PingFang SC;color:#2D8CF0" slot="title">
                          <Icon type="ios-paper" size=16></Icon>
                          表 名 列 表
                        </h3>
                        <Row>
                          <Col>
                          <Table stripe :columns="columns1" :data="data1"></Table>
                          </Col>
                        </Row>
                      </Card>
                  </Content>
                </Layout>
              </Content>
            </Layout>
            <Footer class="layout-footer-center">2018-2019 create by bq&xq</Footer>
          </Layout>
        </div>
    </div>
</template>

<script>

    export default {
        name: 'main',
        props: {},
        data() {
            return {
                msg: 'main',
              columns1: [
                {
                  title: '表名',
                  key: 'table_name'
                },
                {
                  title: '操作',
                  key: 'action',
                  align: 'center',
                  render: (h, params) => {
                    return h('div', [
                      h('Button', {
                        props: {
                          type: 'primary',
                          size: 'small',
                        },
                        style: {
                          marginRight: '5px',
                        },
                        on: {
                          click: () => {

                          },
                        },
                      }, '生成bean')
                    ]);
                  },
                },
              ],
              data1: [
                {
                  table_name: 'John Brown',
                },
                {
                  table_name: 'Jim Green',
                },
                {
                  table_name: 'Joe Black',
                },
                {
                  table_name: 'Jon Snow',
                }
              ]
            };
        },
        components: {},
        computed: {},
        methods: {},
        beforeCreate: function () {
        },
        mounted: function () {
        }
    };
</script>

<style scoped>
    .main {
    }
</style>
